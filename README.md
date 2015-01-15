A series of useful commands written in python to interact with a MySQL Server running on Docker

# Motivation
Docker is awesome, but when using MySQL on a Dockerized environment simple tasks can become commands with lots of options and arguments.

__Note:__ The following commands will use the official MySQL docker image found at https://registry.hub.docker.com/_/mysql/

# Commands provided

	dmysql-server (Start a new MySQL Server)
	dmysql-server-rm (Remove a MySQL Server)
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

`dmysql-server-rm CONTAINERNAME` : remove a MySQL server (ie run `docker rm -v`); the default is to remove volumes associated directly with the server container

`dmysql-server-rm` options:

* `-f` : force containers to stop to allow them to be deleted
* `--preserve-volume` : retain the volume mounted directly on a server container
* `--with-volume` : also remove an automatically named linked data volume container
* `--volume-name` : also remove an explicitly named linked data volume container

Note that `--preserve-volume` means that `--with-volume` and `--volume-name` are ignored

# Install
Clone or download this project then run:

	$ cd directory_with_scripts
	$ sudo chmod +x dmysql*
	$ sudo cp dmysql* /usr/local/bin

# License
Released under the MIT License