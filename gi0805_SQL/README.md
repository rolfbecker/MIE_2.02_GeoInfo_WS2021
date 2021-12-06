# Install PostgreSQL #

**PostgreSQL** is the most advanced open source object relational database management system. 
<br>Download and install it from [www.postgresql.org](https://www.postgresql.org/)

As GUI based admin tool **pgAdmin4** will be used. 
<br>Download and install it from [www.pgadmin.org](https://www.pgadmin.org/)

# Database Setup #

## Create users and database for environmental monitoring applications ##

Create new users and a new database which we will use for first exercises to get used to SQL and relational algebra (RA). Later we will use the setup to manage environmental data. The environmental database is named `env_db` and the related users `env_master` and `env_user`, respectively.

Open a command line interface, e.g. by running `cmd` or open the *Anaconda Powershell Prompt* on Windows or open a terminal under Linux.

**Change to the subdirectory with the SQL scripts**, i.e [./sql_scripts/](./sql_scripts/). The SQL scripts have the extension *.sql. 
Read the code in the scripts. Open the scripts in your favorite editor.

**Change and remember the passwords in the SQL script** creating the users: [./sql_scripts/010_create_users_for_env_db_V001.sql](./sql_scripts/010_create_users_for_env_db_V001.sql)

Be sure you know the host your postgres database resides on (e.g. localhost) and the password of user postgres.

To create new database users connect as (U)ser postgres (superuser) to the maintence (d)atabase postgres by executing

	psql -h localhost -U postgres -d postgres -f 010_create_users_for_env_db_V001.sql

The command line options define: `-h` host (i.e. the server the DB is running on), `-U` user (postgres is the DB superuser), `-d` database (postgres is name of the maintenance database), and `-f` the file with the SQL commands to be executed.

Now let us create the new database `env_db`:

	psql -h localhost -U postgres -d postgres -f 020_create_database_env_db_V001.sql

## Create relations "Bar" and "Sells" used in the presentation on Relational Algebra ##

Now use the new DB user `env_user` to create the tables (relations) in the new database `env_db` used for the first exercises.

Have a look at the SQL script creating the tables for the _bar example_ of the RA presentation.




