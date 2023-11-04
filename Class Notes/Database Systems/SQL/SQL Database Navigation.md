[[SQL Commands]] used to navigate SQL tables:

**To View Columns of a Table**
SELECT [Column_name] FROM [Table_name]

add LIMIT [Number_Of_Rows] to the end to only print x rows

- Use * to select all columns


You can use arithmetic in SELECT statements
- Operators
	- Multiplication: *
	- Division: /
	- Integer division: DIV
	- Modulo (remainder): % or MOD
	- Addition: +
	- Subtraction: -
- Precedence
	- Multiplication, division, modulo
	- Addition, Subtraction
	- Can control using parenthesis


**Use of Distinct**
SELECT DISTINCT [column] FROM [table]
**Use of BETWEEN**
- example:
WHERE national_day BETWEEN "1990-01-01" AND "1990-12-31"

**Use of WHERE Clause**
- example:
	SELECT name 
	FROM countries
	WHERE region_id = 15;

**Comparison Operators**
- Equality: =
- Less than: <
- greater than: >
- less than or equal to: <=
- greater than or equal to: >=
**Logical Operators for Compound Search Conditions**
- AND
- OR
- NOT