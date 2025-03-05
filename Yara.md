Pattern matching tool to find malware

Basic usage
`yara [.YAR RULE FILE] [TARGET DIRECTOR?FILE]`

### Yara Rule Files
Rule to search for strings
```bash
rule helloworld_checker{
	strings:
		$hello_world = "Hello World!"
		$string_lower = "hello world"
		$string_upper = "HELLO WORLD"

	condition:
		any of them
}
```