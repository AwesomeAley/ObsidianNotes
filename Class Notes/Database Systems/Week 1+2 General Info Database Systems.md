

**Data:** describes real-world systems
characteristics of data
	- scope
	- format
	- access
Analog vs Digital


#### Data vs. Information

information is important as it leads to knowledge and fuels decision making


History of data storage
- file cabinets
- file systems
- modern databases

File based systems: collection of application programs the preform services for end users.

Each program defines and manages its own data
	- File systems considered data as records consisting of fields
	- but even more complex because fields are typically of a fixed lenght or require a delimiter
Groups of related records are called files

Limitations of File-Based Approach
- Separation and isolation of data
- duplication of data
- incompatible file formats
- data and structural dependencies: code is preset for expected structure of data
- fixed queries/proliferation of application programs
- concurrency: multiple programs accessing and altering the same program at the same time


**Database** : A collection of data in a structured format

DBMS (Database management systems)Requirements:
- Performance
- Authorization
- Security
- Rules
- Recovery - Have to be able to recover from failure


**Transactions** : Is a group of queries that must be either completed or rejected as a whole
 - Manage concurrency
 - DBMS Must
	 - Insure that transactins are processed completely or not at all
	 - Prevent conflict between concurrent transactions
	 - Ensure transactions are never lost


**Query** : A command for a database
**Query Language** : A computer programming language for writing database queries 

**SQL** : Structured Query Language contains commands to 
	Insert, update, retrieve and delete data
	Create, modify, and delete databases

**Database Design and Programming**
Three design phases
	- Analysis
	- Logical design
	- Physical Design
Programming
	- SQL is not a programming language
	- API


MYSQL


**How is data stored in a database?**
Different types of models
- conceptual: what is stored, and how
- logical: how data is organized
- physical: how data is stored physically

