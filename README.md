# DZD - OMOP CDM Python ORM/Data Classes Representation
A Python ORM/data classes representation of the [Observational Medical Outcomes Partnership (OMOP) Common Data Model (CDM)](https://www.ohdsi.org/data-standardization/) in different flavors powered by [sqlacodegen](https://github.com/agronholm/sqlacodegen)

Author/Maintainer: Tim Bleimehl  
Status: Proof of Concept successfull. Working towards a Beta Version  


- [DZD - OMOP CDM Python ORM/Data Classes Representation](#dzd---omop-cdm-python-ormdata-classes-representation)
- [Kudos](#kudos)
- [Whats in the package?](#whats-in-the-package)
  - [OMOP Python classes code generator](#omop-python-classes-code-generator)
  - [OMOP Python ORM/Data Classes modules](#omop-python-ormdata-classes-modules)
  - [What are ORM/Data classes? And why should i use them?](#what-are-ormdata-classes-and-why-should-i-use-them)
- [Data classes flavors](#data-classes-flavors)
- [how to install DZD OMOP Models](#how-to-install-dzd-omop-models)
- [How to use this DZD OMOP Models](#how-to-use-this-dzd-omop-models)



# Kudos

* This project uses sqlacodegen for the data class generation ❤️ Thanks for the great work of the community at https://github.com/agronholm/sqlacodegen
* Thanks to the great communitiy at https://www.ohdsi.org/data-standardization/ and https://github.com/OHDSI/CommonDataModel for the OMOP data model
* Thanks to the thousands of layers (we can not list here) of software dev shoulders we stand on as python devs ❤️ 

# Whats in the package?

This projects consists of two parts:

## OMOP Python classes code generator
The first one is the code generator that generates Python data classes based on the OMOP CDM.
Usually you wont need to interact with this part of the project, if you just want to work with the OMOP data classes.  

If you are interested have a look at the dedicated [README](README_codegen.md)

## OMOP Python ORM/Data Classes modules

This is propably the interesting stuff for you! We provide the OMOP CDM as [sqlalchemy](https://www.sqlalchemy.org/) ORM and sqlmodel classes.


## What are ORM/Data classes? And why should i use them?

Oh boy! Have you even lived before? Lets bring you on board!

A data class in Python, particularly within the context of Object-Relational Mapping (ORM), is a class designed to represent and manipulate data from a database. These classes define the structure and types of the data they manage. In ORM frameworks like SQLAlchemy and SQLModel, data classes map class attributes to database columns, enabling seamless CRUD operations through Python objects. They facilitate database schema creation, querying, and data validation while abstracting the complexity of raw SQL queries.

That's sounds fancy but lets at the real life impact ORM Classes can have for you:

* **Easy Database Use**: Instead of developing complex SQL queries, you can use simple Python code to interact with your database. This makes it much easier to add, remove, or change data.
* **Clear and Organized Code**: Using Data classes help you keep your code neat and organized. Each class represents a table, making it easy to see what data you have and how it’s structured.
* **Better Tools Support**: Many coding tools and editors can help you write and debug your code better when you use data classes. This includes features like suggestions and error checking, making coding easier and more fun.
* **Data Validation**: Because ORM classes specify the datamodel, you can not enter wrong datatypes. You can immediate feedback where and what was entered on a wrong location (Or when required data is missing.)
* **Integration with Data Analysis Libraries**: Python has powerful libraries for data analysis (like pandas and NumPy) that integrate well with ORMs. This allows you to easily query the OMOP CDM database and directly use the results for analysis.

There are many more great and subtil advantages, but lets keep it short here. In summary, using ORM classes simplifies database management, makes your code more understandable, speeds up development, ensures data quality, and provides better tool support. 



# Data classes flavors

There are different styles of data model represantation possible. This module covers four popular of them. They are all based on (or directly integrated in) https://www.sqlalchemy.org/ 
sqlalchemy is the most common way to inetract with relational databases in python. Lets have an overview how the different styles are named, have a short explanation what they are and where you can find the respective omop representation:

* `tables` ([OMOP CDM 5.3](OMOPModel/OMOP_CDM_5.3_tables.py), [OMOP CDM 5.4](OMOPModel/OMOP_CDM_5.4_tables.py)): only basic `Table` objects that represant the OMOP CDM. No real ORM functionality. if you dont have a specific reason to use these, ignore it.
* `declarative` ([OMOP CDM 5.3](OMOPModel/OMOP_CDM_5.3_declarative.py), [OMOP CDM 5.4](OMOPModel/OMOP_CDM_5.4_declarative.py)): the default way to declare table based data classes in sqlalchemy; generates classes inheriting from `declarative_base()`. See https://docs.sqlalchemy.org/en/20/orm/quickstart.html#declare-models for more details behind the scenes. if you are an old sqlalchemy veteran, you may want to have a look at these.
* `dataclasses` ([OMOP CDM 5.3](OMOPModel/OMOP_CDM_5.3_dataclasses.py), [OMOP CDM 5.4](OMOPModel/OMOP_CDM_5.4_dataclasses.py)): The more modern (2.0) approach of sqlalchemy representation of ORM/data classes. https://docs.sqlalchemy.org/en/20/orm/dataclasses.html 
* `sqlmodels` ([OMOP CDM 5.3](OMOPModel/OMOP_CDM_5.3_sqlmodels.py), [OMOP CDM 5.4](OMOPModel/OMOP_CDM_5.4_sqlmodels.py)): (Chef's recommendation 😘🤌 ) - [sqlmodel](https://sqlmodel.tiangolo.com/) is the kid on the block. Its a project by the [Pydantic](https://docs.pydantic.dev/latest/) community. It unites sqlalchemy and Pydantic. Two of the most beatiful and useful python module out there. My personal favorite!

# how to install DZD OMOP Models

todo

# How to use this DZD OMOP Models

todo

