# Id Generation in JPA
The @GeneratedValue annotation in JPA (Java Persistence API) is used to specify the strategy used for generating primary key values for entities. The GenerationType.IDENTITY strategy is commonly used with databases that support auto-incrementing columns, such as MySQL and PostgreSQL.

Here’s a breakdown of the parameters you can use with @GeneratedValue(strategy = …):

1. GenerationType.IDENTITY:
This strategy relies on an auto-incremented database column for primary key generation.
It is suitable for databases that support auto-incrementing columns (e.g., MySQL, PostgreSQL).
The database automatically generates a unique value for the primary key when a new record is inserted.

2. GenerationType.SEQUENCE:
This strategy relies on a database sequence to generate primary key values.
Not all databases support sequences, so it’s essential to check database compatibility.
You may need to define the sequence explicitly in your database.

3. GenerationType.TABLE:
This strategy uses a separate table to maintain a counter for generating primary key values.
It can be less efficient than other strategies and is not commonly used.

4. GenerationType.AUTO:
The AUTO strategy allows the JPA provider to choose the appropriate strategy based on the underlying database capabilities.
It’s a portable way to generate primary keys, but the actual strategy used depends on the database.



## Demonstration of Id Generation in JPA through code

For this I have created one Customer Entity.

use @Id and @GenreatedValue strategy auto.

One Customer Repository for performing basic CRUD opreations.

Written Test Cases.

Use MySql Database for storing customer table.

### Commands Used in MySQL Workbench -

use sys;

CREATE TABLE customer_table ( id int PRIMARY KEY auto_increment, name varchar(20), email varchar(20) );

select * from customer_table;
