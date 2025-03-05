Pattern matching tool to find malware

Basic usage
`yara [.YAR RULE FILE] [TARGET DIRECTORY]`

### Yara Rule Files
Rule to search for strings
```bash

rule helloworld_checker{
	strings:
		$hello_world = "Hello World!"
		$string_lower = "hello world"
		$string_upper = "HELLO WORLD"

	condition:
		any of them and filesize < 10KB
}
```

![[Pasted image 20250305105617.png]]

### LOKI
Open source tool for advanced YARA scans
https://github.com/Neo23x0/Loki/releases

Loki Yara rules are stored in
`~/Loki/signature-base/yara`

Navigate to Loki directory
`cd ~/Loki/`
Update signature base directory
`--update`
Run Loki 
`python -loki.py -h`

Scan with Loki
`python ~/Loki/loki.py -p [TARGET DIRECTORY]`

