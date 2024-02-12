#python 
Functions are defined using the keyword *def*

```Python
def count(data, target):
	n = 0
	for item in data:
		if item == target:
			n+=1
	return n
```

This establishes a new identifier as the name of the function (count) as well as the signature (the variables expected as input when calling the function).

**Information passing**: follows the semantics of the standard assignment statement
	prizes = count(grades, 'A')
This is the same as 
	data = grades
	target = 'A'
[


