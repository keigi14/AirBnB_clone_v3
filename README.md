**HBNB - The Console**

This repository encompasses the initial phase of a student project aimed at constructing a replica of the AirBnB website. In this phase, a backend interface, known as the console, has been developed to manage program data. The console commands empower users to create, update, and delete objects, along with overseeing file storage. Through the utilization of JSON serialization/deserialization, the storage system ensures persistence across different sessions.

---

**Repository Contents by Project Task**

| Tasks | Files | Description |
| ----- | ----- | ------ |
| 0: Authors/README File | [AUTHORS](https://github.com/Desire-2/AirBnB_clone_v2/blob/main/AUTHORS) | Project authors |
| 1: Pep8 | N/A | All code is pep8 compliant|
| 2: Unit Testing | [/tests](https://github.com/Desire-2/AirBnB_clone/tree/dev/tests) | All class-defining modules are unittested |
| 3. Make BaseModel | [/models/base_model.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/base_model.py) | Defines a parent class to be inherited by all model classes|
| 4. Update BaseModel w/ kwargs | [/models/base_model.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/base_model.py) | Add functionality to recreate an instance of a class from a dictionary representation|
| 5. Create FileStorage class | [/models/engine/file_storage.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/_ _init_ _.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/__init__.py) [/models/base_model.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/base_model.py) | Defines a class to manage persistent file storage system|
| 6. Console 0.0.1 | [console.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/console.py) | Add basic functionality to console program, allowing it to quit, handle empty lines and ^D |
| 7. Console 0.1 | [console.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/console.py) | Update the console with methods allowing the user to create, destroy, show, and update stored data |
| 8. Create User class | [console.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/engine/file_storage.py) [/models/user.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/user.py) | Dynamically implements a user class |
| 9. More Classes | [/models/user.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/user.py) [/models/place.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/place.py) [/models/city.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/city.py) [/models/amenity.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/amenity.py) [/models/state.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/state.py) [/models/review.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/review.py) | Dynamically implements more classes |
| 10. Console 1.0 | [console.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/console.py) [/models/engine/file_storage.py](https://github.com/Desire-2/AirBnB_clone/blob/dev/models/engine/file_storage.py) | Update the console and file storage system to work dynamically with all  classes update file storage |

<br>
<br>

**General Use**

1. Initially, clone this repository.

3. Once cloned, locate the "console.py" file and execute it as follows:
```
/AirBnB_clone$ ./console.py
```
4. Upon running this command, the following prompt should be displayed:
```
(hbnb)
```
5. This prompt indicates that you are in the "HBnB" console, where various commands are available.

**Commands**
- `create`: Creates an instance based on the given class
- `destroy`: Destroys an object based on class and UUID
- `show`: Shows an object based on class and UUID
- `all`: Shows all objects the program has access to, or all objects of a given class
- `update`: Updates existing attributes of an object based on class name and UUID
- `quit`: Exits the program (EOF will as well)

**Alternative Syntax**
Users can issue console commands using an alternative syntax:

Usage: `<class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])`

Advanced syntax is implemented for the following commands:
- `all`: Shows all objects the program has access to, or all objects of a given class
- `count`: Returns the number of object instances by class
- `show`: Shows an object based on class and UUID
- `destroy`: Destroys an object based on class and UUID
- `update`: Updates existing attributes of an object based on class name and UUID

<br>
<br>

**Examples**

**Primary Command Syntax**

**Example 0: Create an object**
Usage: `create <class_name>`
```
(hbnb) create BaseModel
```
```
(hbnb) create BaseModel
3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb)                   
```

**Example 1: Show an object**
Usage: `show <class_name> <_id>`
```
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
[BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
(hbnb)  
```

**Example 2: Destroy an object**
Usage: `destroy <class_name> <_id>`
```
(hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb) show BaseModel 3aa5babc-ef

b6-4041-bfe9-3cc9727588f8
** no instance found **
(hbnb)   
```

**Example 3: Update an object**
Usage: `update <class_name> <_id>`
```
(hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
(hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
[BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729889), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
(hbnb)
```

**Alternative Syntax**

**Example 0: Show all User objects**
Usage: `<class_name>.all()`
```
(hbnb) User.all()
["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571128115b', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

**Example 1: Destroy a User**
Usage: `<class_name>.destroy(<_id>)`
```
(hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

**Example 2: Update User (by attribute)**
Usage: `<class_name>.update(<_id>, <attribute_name>, <attribute_value>)`
```
(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", name "Todd the Toad")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'name': 'Todd the Toad', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

**Example 3: Update User (by dictionary)**
Usage: `<class_name>.update(<_id>, <dictionary>)`
```
(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
---

<center> <h2>Additional Information</h2> </center>

This project is structured with specific tasks assigned to each file, contributing to the overall development of the AirBnB clone. The README file provides essential information about project authors, while compliance with Pep8 ensures code consistency. Unit testing, carried out in the '/tests' directory, validates the functionality of class-defining modules.

Tasks 3 to 10 involve the creation and enhancement of specific classes and functionalities within the console. For instance, Task 3 establishes the foundational `BaseModel` class, while Task 4 extends its capabilities by allowing instances to be recreated from dictionary representations.

The introduction of the `FileStorage` class in Task 5 manages the persistent file storage system through collaborative efforts in multiple files. Subsequent tasks focus on refining the console, supporting dynamic interactions with various classes, and extending the range of dynamically implemented classes.

---

**General Use Instructions**

1. **Clone the Repository:** Begin by cloning the repository to your local environment.

2. **Locate and Run "console.py":** Navigate to the cloned repository and find the "console.py" file. Run it using the following command:
   ```
   /AirBnB_clone$ ./console.py
   ```
3. **Access the Console:** Upon running the command, the console prompt `(hbnb)` will appear, indicating that you are in the "HBnB" console.

4. **Console Commands:**
   - **`create`**: Create an instance based on the given class.
   - **`destroy`**: Destroy an object based on class and UUID.
   - **`show`**: Show an object based on class and UUID.
   - **`all`**: Show all objects the program has access to, or all objects of a given class.
   - **`update`**: Update existing attributes of an object based on class name and UUID.
   - **`quit`**: Exit the program (EOF will as well).

5. **Alternative Syntax:**
   - Users can issue console commands using an alternative syntax:
   ```
   Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])
   ```

   - Advanced syntax is implemented for commands such as `all`, `count`, `show`, `destroy`, and `update`.

---

<center> <h2>Examples</h2> </center>

**Primary Command Syntax**

**Example 0: Create an object**
Usage: `create <class_name>`
```
(hbnb) create BaseModel
```
```
(hbnb) create BaseModel
3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb)                   
```

**Example 1: Show an object**
Usage: `show <class_name> <_id>`
```
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
[BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
(hbnb)  
```

**Example 2: Destroy an object**
Usage: `destroy <class_name> <_id>`
```
(hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
** no instance found **
(hbnb)   
```

**Example 3: Update an object**
Usage: `update <class_name> <_id>`
```
(hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
(hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
[BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729889), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
(hbnb)
```

**Alternative Syntax**

**Example 0: Show all User objects**
Usage: `<class_name>.all()`
```
(hbnb) User.all()
["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571128115b', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

**Example 1: Destroy a User**
Usage: `<class_name>.destroy(<_id>)`
```
(hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

**Example 2: Update User (by attribute)**
Usage: `<class_name>.update(<_id>, <attribute_name>, <attribute_value>)`
```
(hbnb) User.update("98bea5de-9cb0-4

d78-8a9d-c4de03521c30", name "Todd the Toad")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'name': 'Todd the Toad', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

**Example 3: Update User (by dictionary)**
Usage: `<class_name>.update(<_id>, <dictionary>)`
```
(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```

---

This comprehensive guide outlines the structure of the AirBnB clone project, its tasks, and provides examples of using the console for various operations. Users can now confidently interact with the console, create, manipulate, and manage objects within the system.
# AirBnB Clone - MySQL

## Group Project

This project is a collaborative effort involving Python, Object-Oriented Programming (OOP), back-end development, SQL, MySQL, and SQLAlchemy. The goal is to create an AirBnB clone using MySQL as the database.

**By:** Guillaume

**Weight:** 2

**Team:** Bosworth Onyema, Desire Bikorimana

**Project Timeline:**
- Start: Jan 12, 2024, 6:00 AM
- End: Jan 18, 2024, 6:00 AM
- Checker Release: Jan 13, 2024, 6:00 PM
- Auto Review: Will be launched at the deadline

## Background Context

Environment variables play a crucial role in this project. The following variables should be utilized:

- `HBNB_ENV`: Running environment, can be "dev" or "test" for now ("production" soon!)
- `HBNB_MYSQL_USER`: Username of your MySQL
- `HBNB_MYSQL_PWD`: Password of your MySQL
- `HBNB_MYSQL_HOST`: Hostname of your MySQL
- `HBNB_MYSQL_DB`: Database name of your MySQL
- `HBNB_TYPE_STORAGE`: Type of storage used, can be "file" (using FileStorage) or "db" (using DBStorage)

## Resources

Read or watch the following resources for a better understanding of the project:

- `cmd` module
- Packages concept page
- `unittest` module
- `args`/`kwargs`
- SQLAlchemy tutorial
- How To Create a New User and Grant Permissions in MySQL
- Python3 and environment variables
- SQLAlchemy
- MySQL 8.0 SQL Statement Syntax

## Learning Objectives

By the end of this project, you should be able to explain the following concepts without the help of Google:

### General
- What is Unit testing and how to implement it in a large project
- What is `*args` and how to use it
- What is `**kwargs` and how to use it
- How to handle named arguments in a function
- How to create a MySQL database
- How to create a MySQL user and grant it privileges
- What ORM means
- How to map a Python Class to a MySQL table
- How to handle 2 different storage engines with the same codebase
- How to use environment variables

## Copyright - Plagiarism

You are responsible for developing solutions for the tasks outlined in this project. Do not copy and paste someone else's work. Publishing project content is strictly forbidden and will result in removal from the program.

## Requirements

### Python Scripts

- Allowed editors: `vi`, `vim`, `emacs`
- Interpreted/compiled on Ubuntu 20.04 LTS using `python3` (version 3.8.5)
- All files end with a new line
- The first line of all files should be exactly `#!/usr/bin/python3`
- A `README.md` file at the root of the project folder is mandatory
- Code should use `pycodestyle` (version 2.8.*)
- All files must be executable
- File length will be tested using `wc`
- All modules should have documentation (`python3 -c 'print(__import__("my_module").__doc__)'`)
- All classes should have documentation (`python3 -c 'print(__import__("my_module").MyClass.__doc__)'`)
- All functions (inside and outside a class) should have documentation (`python3 -c 'print(__import__("my_module").my_function.__doc__)'` and `python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'`)
- Documentation should be a real sentence explaining the purpose of the module, class, or method

### Python Unit Tests

- Allowed editors: `vi`, `vim`, `emacs`
- All test files should end with a new line
- All test files should be inside a folder `tests`
- Use the `unittest` module
- Test files should be python files (extension: `.py`)
- Test files and folders should start with `test_`
- File organization in the `tests` folder should be the same as the project structure
- All tests should be executed by using the command: `python3 -m unittest discover tests`
- Modules, classes, and functions should have documentation as described above
- Collaborate on test cases to ensure coverage

### SQL Scripts

- Allowed editors: `vi`, `vim`, `emacs`
- Files executed on Ubuntu 20.04 LTS using MySQL 8.0
- Files executed with SQLAlchemy version 1.4.x
- All files end with a new line
- All SQL queries should have a comment just before
- All files should start with a comment describing the task
- All SQL keywords should be in uppercase (`SELECT`, `WHERE`, etc.)
- A `README.md` file at the root of the project folder is mandatory
- File length will be tested using `wc`

### GitHub

- One project repository per group
- Do not clone/fork a partner’s project repository with the same name before the second deadline

## Tasks

### 0. Fork me if you can!

1. Fork the existing codebase.
2. Update the repository name to `AirBnB_clone_v2`.
3. Update the `README.md` with your information without deleting the initial authors.

### 1. Bug free!

- Ensure all unittests pass without errors.
- PEP8 should be adhered to.
- Some tests may be irrelevant for certain storage types; skip them using the `skipIf` feature.
- Collaborate on test cases to cover edge cases.

### 2. Console improvements

- Update the `do_create` function in `console.py` to allow object creation with parameters.
- Command syntax: `create <Class name> <param 1> <param 2> <param 3>...`
- Param syntax: `<key name>=<value>`
- Values can be strings, floats, or integers. Follow the specified syntax.
- Add tests for this new feature.

### 3. MySQL setup development

- Write a script to prepare a MySQL server for development.
- Create a database `hbnb_dev_db`.
- Create a new user `hbnb_dev` with the password `hbnb_dev_pwd`.
- Grant all privileges to `hbnb_dev` on `hbnb_dev_db`.
- Grant SELECT privilege on `performance_schema` to `hbnb_dev`.

### 4. MySQL setup test

- Write a script to prepare a MySQL server for testing.
- Create a database `hbnb_test_db`.
- Create a new user `hbnb_test` with the password `hbnb_test_pwd`.
- Grant all privileges to `hbnb_test` on `hbnb_test_db`.
- Grant SELECT privilege on `performance_schema` to `hbnb_test`.

### 5. Delete object

- Update `FileStorage` (`models/engine/file_storage.py`).
- Add a new public instance method: `def delete(self, obj=None)`.
- If `obj` is not `None`, delete it from `__objects`.
- Update the prototype of `def all(self)` to `def all(self, cls=None)` to allow optional filtering

 of objects by class.
- Update the prototype of `def new(self, obj)` to `def new(self, obj=None)` to allow the storage of `None` objects.
- Update the prototype of `def save(self)` to `def save(self, cls=None)` to allow saving only objects of a certain class.
- Add new public instance method: `def reload(self)` to reload objects from the file (only if the file exists).
- Add new private instance attribute `__objects` to store objects by `<class name>.id`.
- Update the prototype of `def save(self)` to `def save(self, cls=None)` to allow saving only objects of a certain class.

### 6. DBStorage - States and Cities

- Update `BaseModel` (`models/base_model.py`).
- Create `Base = declarative_base()` before the class definition of `BaseModel`.
- Modify the class `BaseModel` by removing the `id`, `created_at`, and `updated_at` columns.
- Add class attributes:
  - `id`: represents a column containing a unique string (60 characters), can’t be null, and is a primary key.
  - `created_at`: represents a column containing a datetime, can’t be null, and has a default value of the current datetime.
  - `updated_at`: represents a column containing a datetime, can’t be null, and has a default value of the current datetime.
- Move `models.storage.new(self)` from `__init__` to `save` and call it just before `models.storage.save()`.
- In `__init__`, manage `kwargs` to create instance attributes from the dictionary.
- Update `to_dict()` to remove the key `_sa_instance_state` from the dictionary if it exists.
- Add a new public instance method: `def delete(self)` to delete the current instance from the storage (`models.storage`) by calling the method `delete`.
- Update `City` (`models/city.py`).
- Modify the class `City` to inherit from `BaseModel` and `Base`.
- Add or replace in the class `City`:
  - `__tablename__`: represents the table name, `cities`.
  - `name`: represents a column containing a string (128 characters), can’t be null.
  - `state_id`: represents a column containing a string (60 characters), can’t be null, and is a foreign key to `states.id`.
- Update `State` (`models/state.py`).
- Modify the class `State` to inherit from `BaseModel` and `Base`.
- Add or replace in the class `State`:
  - `__tablename__`: represents the table name, `states`.
  - `name`: represents a column containing a string (128 characters), can’t be null.
  - `cities`: for `DBStorage`, class attribute `cities` must represent a relationship with the class `City`. If the `State` object is deleted, all linked `City` objects must be automatically deleted. Also, the reference from a `City` object to his `State` should be named `state`. For `FileStorage`, add a getter attribute `cities` that returns the list of `City` instances with `state_id` equals to the current `State.id`.
- Update `DBStorage` (`models/engine/db_storage.py`).
- Add private class attributes:
  - `__engine`: set to `None`.
  - `__session`: set to `None`.
- Add public instance methods:
  - `__init__(self)`: create the engine (`self.__engine`). The engine must be linked to the MySQL database and user created before (`hbnb_dev` and `hbnb_dev_db`).
    - Dialect: `mysql`.
    - Driver: `mysqldb`.
    - All values must be retrieved via environment variables:
      - MySQL user: `HBNB_MYSQL_USER`.
      - MySQL password: `HBNB_MYSQL_PWD`.
      - MySQL host: `HBNB_MYSQL_HOST` (here = localhost).
      - MySQL database: `HBNB_MYSQL_DB`.
    - Don’t forget the option `pool_pre_ping=True` when you call `create_engine`.
    - Drop all tables if the environment variable `HBNB_ENV` is equal to `test`.
  - `all(self, cls=None)`: query on the current database session (`self.__session`) all objects depending on the class name (argument `cls`). If `cls` is `None`, query all types of objects (User, State, City, Amenity, Place, and Review). This method must return a dictionary where:
    - Key = `<class-name>.<object-id>`.
    - Value = object.
  - `new(self, obj)`: add the object to the current database session (`self.__session`).
  - `save(self)`: commit all changes of the current database session (`self.__session`).
  - `delete(self, obj=None)`: delete from the current database session `obj` if not `None`.
  - `reload(self)`: create all tables in the database (feature of SQLAlchemy). (WARNING: all classes that inherit from `Base` must be imported before calling `Base.metadata.create_all(engine)`).
- Update `__init__.py` (`models/__init__.py`).
- Add a conditional depending on the value of the environment variable `HBNB_TYPE_STORAGE`.
  - If equal to `db`, import `DBStorage` class in this file.
  - Create an instance of `DBStorage` and store it in the variable `storage` (the line `storage.reload()` should be executed after this instantiation).
  - Else, import `FileStorage` class in this file.
  - Create an instance of `FileStorage` and store it in the variable `storage` (the line `storage.reload()` should be executed after this instantiation).
  - This “switch” will allow you to change storage type directly by using an environment variable.

### 7. DBStorage - User

- Update `User` (`models/user.py`).
- Modify the class `User` to inherit from `BaseModel` and `Base`.
- Add or replace in the class `User`:
  - `__tablename__`: represents the table name, `users`.
  - `email`: represents a column containing a string (128 characters), can’t be null.
  - `password`: represents a column containing a string (128 characters), can’t be null.
  - `first_name`: represents a column containing a string (128 characters), can be null.
  - `last_name`: represents a column containing a string (128 characters), can be null.
  

## 8. Deploy static

Your project is ready! It’s time to deploy it to your server. You will host it on your server at this IP: 54.157.142.165. You have to make sure you’re deploying the right project. The project folder should be named `AirBnB_clone_v2` (the name of your repository). Use the `scp` command to transfer the folder.

```bash
scp -r AirBnB_clone_v2 ubuntu@<your-server-ip>:/home/ubuntu/
```

You will be prompted for the password. Enter it to complete the transfer. Once the transfer is complete, connect to your server and navigate to the project folder:

```bash
ssh ubuntu@<your-server-ip>
cd AirBnB_clone_v2
```

Now, you need to set up your environment variables on the server. Open the `.bashrc` file:

```bash
nano ~/.bashrc
```

Add the following lines to the end of the file, replacing the values with your database information:

```bash
export HBNB_MYSQL_USER="<your-mysql-user>"
export HBNB_MYSQL_PWD="<your-mysql-password>"
export HBNB_MYSQL_HOST="<your-mysql-host>"
export HBNB_MYSQL_DB="<your-mysql-database>"
export HBNB_ENV="production"
export HBNB_TYPE_STORAGE="db"
```

Save the file and exit the editor. Now, reload the `.bashrc` file to apply the changes:

```bash
source ~/.bashrc
```

Your environment variables are now set on the server. It's time to deploy your project.

## 9. Initial deploy

1. Install the required packages:

```bash
sudo apt-get update
sudo apt-get install -y python3-pip
sudo apt-get install -y python3-mysqldb
sudo apt-get install -y mysql-server
sudo apt-get install -y libmysqlclient-dev
sudo apt-get install -y python3-dev
pip3 install -r requirements.txt
```

2. Initialize the MySQL database:

```bash
echo "create database hbnb_dev_db;" | mysql -u root -p
echo "create user 'hbnb_dev'@'localhost' identified by 'hbnb_dev_pwd';" | mysql -u root -p
echo "grant all privileges on hbnb_dev_db.* to 'hbnb_dev'@'localhost';" | mysql -u root -p
```

3. Run the initial Flask application:

```bash
python3 -m web_dynamic.0-hbnb
```

Visit your server's IP address in a web browser, and you should see your AirBnB clone.

## 10. First API

Create an API that returns the status of your API. The status should include:

- The number of each objects by type.
- The status should be JSON format.

Example:

```json
{
  "amenities": 4,
  "cities": 10,
  "places": 18,
  "reviews": 13,
  "states": 10,
  "users": 24
}
```

The route for this should be `/status/` and the method should be `GET`.

## 11. Place - User and Place - Amenity

Update your classes to handle Place objects:

- `Place` should handle an instance of `Amenity` for each amenity linked.
- `Place` should handle an instance of `User` for each user linked.

Update the database schema and update your MySQL database accordingly.

## 12. More API features!

Add more features to your API:

- `/stats/`: retrieve the number of each objects by type. The endpoint should return a JSON format similar to the one in Task 10.

- `/stats/<class_name>`: retrieve the number of objects of a specific class. The endpoint should return a JSON format similar to the one in Task 10.

## 13. Filter places

Add a new route `/places/<place_id>/reviews` that retrieves the `Review` objects of a `Place`. Use the relationship between `Place` and `Review` to achieve this.

## 14. User

Create a new endpoint `/users/<user_id>` that retrieves a `User` object. This endpoint should return a JSON format similar to the one in Task 10.

## Deadline
Jan 24, 2024, 6:00 AM
