#python 
Exceptions are unexpected events that occur during the execution of a program. This might result from a logical error or an unanticipated situation. These exceptions are objects that are raised (or thrown) by code that encounters an unexpected circumstance

### Raising an Exception

An exception is thrown by executing the raise statement, with an appropriate instance of an exception class as an argument that designates the problem.

For example, if a function for computing the square root is sent a negative value as a parameter, it can raise an exception with the command:

	raise ValueError('x cannot be nagative')


### Catching an Exception

In Python, exceptions can be tested and caught using a try-except control structure

	try:
		ratio = x/y
	except ZeroDivisionError:
		... do something else...

- In this structure, the "try" block is the primary code to be executed
- Although it is a single command in this example, it can be more
- Following the try "try-block" are one or more "except" cases, each with an identified error type and an indented block of code that should be executed if the designated error is raised within the try-block