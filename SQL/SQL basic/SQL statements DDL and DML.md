SQL statements can be categorized into two main types: Data Definition Language (DDL) and Data Manipulation Language (DML). Here's an overview of each:

1. **Data Definition Language (DDL)**:

   - DDL statements are used to define the structure and schema of a database.

   - Common DDL statements include:

     - **CREATE**: Used to create database objects such as tables, views, indexes, etc.

       ```SQL

       CREATE TABLE table_name (

           column1 datatype,

           column2 datatype,

           ...

       );

       ```

     - **ALTER**: Used to alter the structure of an existing database object.

       ```

       ALTER TABLE table_name

       ADD column_name datatype;

       ```

     - **DROP**: Used to delete objects from the database.

       ```

       DROP TABLE table_name;

       ```

     - **TRUNCATE**: Used to remove all records from a table while preserving the table structure.

       ```

       TRUNCATE TABLE table_name;

       ```

     - **RENAME**: Used to rename an existing database object.

       ```

       RENAME TABLE old_table_name TO new_table_name;

       ```

2. **Data Manipulation Language (DML)**:

   - DML statements are used to manipulate the data stored in the database.

   - Common DML statements include:

     - **SELECT**: Used to retrieve data from one or more tables.

       ```

       SELECT column1, column2

       FROM table_name

       WHERE condition;

       ```

     - **INSERT**: Used to add new records into a table.

       ```

       INSERT INTO table_name (column1, column2)

       VALUES (value1, value2);

       ```

     - **UPDATE**: Used to modify existing records in a table.

       ```

       UPDATE table_name

       SET column1 = value1, column2 = value2

       WHERE condition;

       ```

     - **DELETE**: Used to remove records from a table.

       ```

       DELETE FROM table_name

       WHERE condition;

       ```

These are the basic SQL statements categorized as DDL and DML, which are essential for creating, modifying, and managing data within a database.