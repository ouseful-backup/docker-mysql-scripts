A series of useful commands written in python to interact with a MySQL Server running on Docker

# Motivation
Docker is awesome, but when using MySQL on a Dockerized environment simple tasks can become commands with lots of options and arguments.

__Note:__ The following commands will use the official MySQL docker image found at https://registry.hub.docker.com/_/mysql/

# Commands provided

	dmysql-server (Start a new MySQL Server)
	dmysql (Open the mysql cli)
	dmysql-create-database (Creates a new database)
	dmysql-import-database (Imports a database)

# Usage

`dmysql-server CONTAINERNAME DBROOTPASSWORD` : create a new MySQL server

`dbmysql-server` options:

* `--with-volume` : create a data volume container with an automatically generated name and link to it
* `--volumes-from` : link to an existing, automatically named data volume container
* `--volume-name NAME` or `--volumes-from --volume-name NAME` : link to an existing, explicitly named data volume container
* `--with-volume --volume-name NAME` : create a data volume container with an explicitly provided name and link to it

Note that `--with-volume` and `--volumes-from` are mutually exclusive.


# Install
Clone or download this project then run:

	$ cd directory_with_scripts
	$ sudo chmod +x dmysql*
	$ sudo cp dmysql* /usr/local/bin

# License
Released under the MIT License