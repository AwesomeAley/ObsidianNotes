Installing universal forwarder to send logs to Splunk server
helpful youtube video:
[https://www.youtube.com/watch?v=yl3gY3JEtmU](https://www.youtube.com/watch?v=yl3gY3JEtmU)

### Add splunk user and group

```bash
useradd -m splunkfwd
groupadd splunkfwd
```

### Install 
```
sudo su
export SPLUNK_HOME="/opt/splunkforwarder"
mkdir $SPLUNK_HOME./spl


wget -O splunkforwarder-9.3.1-0b8d769cb912-Linux-x86_64.tgz "https://download.splunk.com/products/universalforwarder/releases/9.3.1/linux/splunkforwarder-9.3.1-0b8d769cb912-Linux-x86_64.tgz"

tar xvzf splunkforwarder-9.3.1-0b8d769cb912-Linux-x86_64.tgz
```

copy contents of /splunkforwarder to /$SPLUNK_HOME once unzipped using tar



### Change owner to the splunk user

``` bash
chown -R splunkfwd:splunkfwd $SPLUNK_HOME
```

### Start 
```bash
sudo $SPLUNK_HOME/bin/splunk start --accept-license
```

### edit or create inputs config file 
location of inputs (and outputs) file:
$SPLUNK_HOME/etc/system/local/inputs.conf)

```

[monitor:///ufhost/var/log]

[fschange:/ufhost/etc/]
fullEvent=true
pollPeriod=60
recurse=true
sendEventMaxSize=10000
index=main

[fschange:/ufhost/var/www]
fullEvent=true
pollPeriod=60
recurse=true
sendEventMaxSize=10000
index=main
```


### connect to receiving indexer 
### Examples:
```

$SPLUNK_HOME/bin/splunk add forward-server idx1.mycompany.com:9997
$SPLUNK_HOME/bin/splunk add forward-server [HOSTNAME OR IP ADDRESS]:[LISTENING PORT]
```

## Linux inputs.conf
Here's a config file that should work on the linux universal forwarders for simple data ingest
```ini
[default]
host = XXX_XXXX_10.0.xxx.xxx

[monitor:///var/log]

[monitor:///var/log/audit]
sourcetype = auditd

[monitor:///var/log/httpd]
sourcetype = httpd

[monitor:///var/log/manual]
sourcetype = manual

[fschange:///etc/]
fullEvent=true
pollPeriod=60
recurse=true
sendEventMaxSize=10000
index=filechange
sourcetype = etc_change

[fschange:///var/www]
fullEvent=true
pollPeriod=60
recurse=true
sendEventMaxSize=10000
index=filechange
sourcetype = www_change

[blacklist:$SPLUNK_HOME/etc/auth]

[blacklist:$SPLUNK_HOME/etc/passwd]

[monitor://$SPLUNK_HOME/var/log/splunk]
index = _internal

[monitor://$SPLUNK_HOME/var/log/watchdog/watchdog.log*]
index = _internal

[monitor://$SPLUNK_HOME/var/log/splunk/license_usage_summary.log]
index = _telemetry

[monitor://$SPLUNK_HOME/var/log/splunk/splunk_instrumentation_cloud.log*]
index = _telemetry
sourcetype = splunk_cloud_telemetry

[monitor://$SPLUNK_HOME/etc/splunk.version]
_TCP_ROUTING = *
index = _internal
sourcetype=splunk_version

[batch://$SPLUNK_HOME/var/run/splunk/search_telemetry/*search_telemetry.json]
move_policy = sinkhole
index = _introspection
sourcetype = search_telemetry
crcSalt = <SOURCE>
log_on_completion = 0

[batch://$SPLUNK_HOME/var/spool/splunk]
move_policy = sinkhole
crcSalt = <SOURCE>

[batch://$SPLUNK_HOME/var/spool/splunk/tracker.log*]
index = _internal
sourcetype = splunkd_latency_tracker
move_policy = sinkhole

[batch://$SPLUNK_HOME/var/spool/splunk/...stash_new]
queue = stashparsing
sourcetype = stash_new
move_policy = sinkhole
crcSalt = <SOURCE>
time_before_close = 0

[batch://$SPLUNK_HOME/var/spool/splunk/...stash_hec]
sourcetype = stash_hec
move_policy = sinkhole
crcSalt = <SOURCE>

[fschange:$SPLUNK_HOME/etc]
disabled = false
#poll every 10 minutes
pollPeriod = 600
#generate audit events into the audit index, instead of fschange events
signedaudit=true
recurse=true
followLinks=false
hashMaxSize=-1
fullEvent=false
sendEventMaxSize=-1
filesPerDelay = 10
delayInMills = 100
```
