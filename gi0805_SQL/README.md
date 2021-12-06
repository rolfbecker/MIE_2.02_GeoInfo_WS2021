# Database Setup #

## Prepare the users and the database for environmental monitoring ##

Let us create new users and a new database which we will use for first exercises to get used to SQL and relational algebra (RA). Later we will use the setup to manage environmental data. The environmental database is named `env_db` and the related users `env_master` and `env_user`, respectively.

Open a command line interface, e.g. run `cmd` or open the *Anaconda Powershell Prompt* on Windows or open a terminal under Linux.

Change directory to where the sql scripts are located, usually in a subdirectory of the material you pulled from the Git repo. The scripts have the extension *.sql. 
Read the code of the scripts. Open the scripts your favorite editor.

**Change and remember the passwords** in the SQL script creating the users!

Be sure you know the host your postgres database resides on (e.g. localhost) and the password of user postgres.

To create new database users connect as (U)ser postgres (superuser) to the maintence (d)atabase postgres by executing

	psql -h localhost -U postgres -d postgres -f 010_create_users_for_env_db_V001.sql

The command line options `-h`, `-U`, `-d`, and `-f` define host (i.e. the server the DB is running on), user (postgres is the DB superuser), database (postgres is name of the maintenance database), and the file with the SQL commands to be executed, respectively. 

Now let us create the new database `env_db`:

	psql -h <host> -U postgres postgres < 020_create_database_env_db_V001.sql

## First (temporary)  relations used in the presentation on Relational Algebra ##

Now use the new DB user `env_user` to create the tables (relations) in the new database `env_db` used for the first exercises.

Have a look at the SQL script creating the tables for the _bar example_ of the RA presentation.



