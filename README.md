# [RoboCon 2020 Workshops](https://robocon.io/#workshops): [TEST AUTOMATION FOR THE ENTERPRISE DATA WAREHOUSE OR TEACHING AN OLD DOG NEW TRICKS!](https://robocon.io/#test-automation-for-the-enterprise-data-warehouse-or-teaching-an-old-dog-new-tricks!)
## Robby the Robot is ready for RoboCon2020 - are you?
![Robby the Robot](src/images/Forbiddenplanetposter.jpg)

# Table of Contents
1. [Introduction](#1-introduction)\
   1.1 [Presenter Bio](#11-presenter-bio)\
   1.2 [Robot Framework](#12-robot-framework)\
   1.3 [Robot Framework Database Library](#13-robot-framework-database-library) 
2. [Preparation](#2-preparation)\
   2.1 [Installation of Python and pip](#21-installation-of-python-and-pip)\
   2.2 [Installation of Robot Framework](#22-installation-of-robot-framework)\
   2.3 [Installation of Robot Framework Database Library](#23-installation-of-robot-framework-database-library)\
   2.4 [Clone GitHub repository for this workshop](#24-clone-github-repository-for-this-workshop)
3. [Python Database API Specification v2.0](#3-python-database-api-specification-v20)\
   3.1 [PEP-249](#31-pep-249)\
   3.2 [A brief introduction to DB-API2](#32-a-brief-introduction-to-db-api2)
4. [Robot Framework Database Library (External)](#4-robot-framework-database-library-external)\
   4.1 [GitHub Repository](#41-github-repository)\
   4.2 [API Documentation](#42-api-documentation)\
   4.3 [List of Interfaces](#43-list-of-interfaces)
5. [Robot Framework Testing with Teradata](#5-robot-framework-testing-with-teradata)\
6. [Teradata Database Library (in-house development @ OP)](#6-teradata-database-library-in-house-development--op)\
7. [Test Automation with Jenkins CI](#7-test-automation-with-jenkins-ci)
8. [IBM InfoSphere DataStage Library (in-house development @ OP)](#8-ibm-infosphere-datastage-library-in-house-development--op)
9. [The future - what are we working on next @ OP?](#9-the-future---what-are-we-working-on-next--op)

## 1. Introduction
The concept of data warehousing dates back to the late 1980s so you would be forgiven for thinking that test automation
has little to offer this domain. OP needed to find a way of improving the quality of DW solutions: enter Robot Framework.
You really can teach an old dog new tricks!
### 1.1 Presenter Bio
* Adrian Yorke is a Senior Data Specialist and DevOps Engineer at OP, one of Finland's largest and oldest Financial groups.
* Driving force behind the adoption of DevOps and Test Automation using Robot Framework in the Data Warehousing tribe.
* During 2019 authored and presented a Python Summer Camp workshop series.
* Tech interests: Python, Raspberry Pi & Open Source projects. Recently I've been studying machine learning and data science.
* When I'm not being a geek: swimming (former national championship swimmer), long distance running (I actually completed
the London marathon!), carpentry & just being there for my daughter and helping her grow.
### 1.2 Robot Framework
[Robot Framework](http://robotframework.org/) is a generic open source automation framework for acceptance testing,
acceptance test driven development (ATDD), and robotic process automation (RPA). It has simple plain text syntax and it
can be extended easily with libraries implemented using Python or Java. The
[Robot Framework User Guide](http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html)
contains all you need to get started and it also covers more advanced topics such as development of your own test libraries.
### 1.3 Robot Framework Database Library
Database Library contains utilities (keywords) meant for Robot Framework's usage. This can allow you to query your
database after an action has been made to verify the results.

## 2. Preparation
### 2.1 Installation of Python and pip
#### Python 2 vs Python 3
Which version of Python should I use?  Check the [wiki](https://wiki.python.org/moin/Python2orPython3) from python.org.
Quite simply, you should be using Python 3 going forward.  Any existing Python 2 code should be converted to Python 3 as
soon as possible which might take some time for large projects.
Python 2 is becoming "End of Life" and the final release will be April 2020. After that date Python 2 will receive no
further official support and you should expect the community to gradually drop support for Python 2.
#### Check which versions of Python and pip (The Python Package Installer) are installed:
`$ python3 --version`\
`$ pip3 --version`
#### If necessary, install pip (The Python Package Installer):
`$ sudo apt update`\
`$ sudo apt install python3-pip`

### 2.2 Installation of Robot Framework
Installation of Robot Framework is documented [here](https://github.com/robotframework/robotframework#installation).
There are two main methods: using pip or installing the latest version from source code.
#### Install using pip:
`$ pip install robotframework`
#### Install by git cloning the repository from GitHub and run setup.py:
`$ git clone https://github.com/robotframework/robotframework.git`

### 2.3 Installation of Robot Framework Database Library
#### Install using pip:
`$ pip install robotframework-database-library`
### 2.4 Clone GitHub repository for this workshop
#### For those that wish to follow along, clone the GitHub repository which contains workshop documentation and examples:
`$ git clone https://github.com/adrianyorke/forbiddenplanet`

## 3. Python Database API Specification v2.0
### 3.1 PEP-249
[PEP 249 -- Python Database API Specification v2.0](https://www.python.org/dev/peps/pep-0249/)
### 3.2 A brief introduction to DB-API2
[A brief introduction to DB-API2](https://cewing.github.io/training.codefellows/lectures/day21/intro_to_dbapi2.html)

## 4. Robot Framework Database Library (External)
Database Library is a [Robot Framework Test Library](https://robotframework.org/#libraries) classed as non-standard or
external library. It was originally designed and implemented by [Franz Allan Valencia See](https://github.com/franz-see)
and is currently maintained by [Jerry Schneider](https://github.com/jerry57).
### 4.1 GitHub Repository
The [Robotframework-Database-Library](https://github.com/franz-see/Robotframework-Database-Library) GitHub repository
contains code and sample test scripts.
### 4.2 API Documentation
The [API Documentation](https://franz-see.github.io/Robotframework-Database-Library/api/0.5/DatabaseLibrary.html) lists
the keywords available in Robot Framework for interactions with databases.
### 4.3 List of Interfaces
[List of Interfaces](https://wiki.python.org/moin/DatabaseInterfaces) documents the database interfaces that have already
been implemented.  If your database is not listed you many need to create your own Robot Framework library to implement
Robot Framework keywords for testing or RPA scripts.  If it is necessary to create your own library, please do consider
sharing with the open source community by submitting a pull request.
### 4.4 Review the tests found in test subfolder
### 4.5 Why SQLite?
SQLite is a fully featured database that ships by default with installations of Python.  There is no server installation or configuration
and the whole database is implemented using only a single file.  Despite this simplicity of design, SQLite is surprising feature rich
and provides and excellent way of learning about database and SQL.  However, SQLite is not recommended for mission-critical Production
implementations.  You should be looking at more robust server database technology such as PostgreSQL for these use cases.
### 4.6 Work through our first robot test suite
Work through SQLite3_DB_Tests.robot and check our installation is working
## 5. Robot Framework Testing with Teradata
Testing with Teradata
2
3
4
5
6

## 6. Teradata Database Library (in-house development @ OP)
Teradata Database Library
2
3
4
5
6

## 7. Test Automation with Jenkins CI
CI
2
3
4
5
6

## 8. IBM InfoSphere DataStage Library (in-house development @ OP)
DataStage
2
3
4
5
6

## 9. The future - what are we working on next @ OP?
Future
2
3
4
5
6
