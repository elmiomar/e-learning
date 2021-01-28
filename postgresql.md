## Setup Postgres

PostgreSQL is a relational database management system that provides an implementation of SQL. It is a popular choice for many small and large projects and recommended for Django applications.

>This guide assumes Linux/Ubunut as operating system.

### Install Postgres

Ubuntu repos contain Postgres packages by default, so we can install Postgres using `apt` tool.

To install Postgres along with its `-contrib` additional utilities, run the following commands:

```
sudo apt update
sudo apt install postgresql postgresql-contrib
```

### Using Postgres

By default, Postgres uses `roles` to handle authentication and authorization. Postgres is set up to use **ident authentication** method, i.e. it associates Postgres roles with a matching Unix/Linux system account.

Postgres creates a user account called **postgres** that is associated with the default Postgres role. In order to use Postgres, you can log into that account.

There are many ways to access this account and use Postgres:

- Switching to the postgres account:

```
sudo -i -u postgres
```

You can now access a Postgres prompt by typing `psql` in the command line. This will log you into the Postgres prompt, and from there you can interact with the database management system.

>Check out this [cheatsheet](https://gist.github.com/Kartones/dd3ff5ec5ea238d4c546)

- Accessing the Postgres prompt without switching accounts:

You can also run the command you’d like with the postgres account directly with `sudo`, like this:

```
sudo -u postgres psql
```

Which will bypass the intermediate shell and log you directly into Postgres prompt.


### Create new roles

You can create new roles from the command line with the `createrole` command:

```
sudo -u postgres createuser --interactive
```

The `--interactive` flag will prompt you for the name of the new role and also ask whether it should have superuser permissions.


### Create a database

To create a database use the `createdb` command:

```
sudo -u postgres createdb sammy
```




