Installig
### Add splunk user and group

```bash
useradd -m splunkfwd
groupadd splunkfwd
```

### Install 
```bash
sudo su
export SPLUNK_HOME="/opt/splunkforwarder"
mkdir $SPLUNK_HOME


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

"
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
"

### connect to receiving indexer 
### Examples:
$SPLUNK_HOME/bin/splunk add forward-server idx1.mycompany.com:9997
$SPLUNK_HOME/bin/splunk add forward-server <host name or ip address>:<listening port>