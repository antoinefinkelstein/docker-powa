# Docker images for PoWA
PoWA, PostgreSQL Workload Analyzer,  is a performance measurement tool for PostgreSQL 9.4+, an open source project developed by [Dalibo](http://www.dalibo.com). I created this project as an easy way to fool around with PoWA and test its capabilities.

_In current state, these images are by no means suitable for production use!_

## Compiled images
Compiled images are available on my [Docker Hub profile](https://hub.docker.com/u/verhage/)

## Current version
The images are based on PoWA 2.0.0 and PostgreSQL 9.4.1.

## The database
The database, in the powa-db folder, is based on the [official PostgreSQL image](https://registry.hub.docker.com/_/postgres/).

### pg_hba.conf
The following line is added to pg_hba.conf to enable password login for any user, from anywhere:

    host all all 0.0.0.0/0 md5

When running the image, don't forget to supply your superuser (the one you'll be accessing the GUI with) with a password!

## The GUI
The powa-web image runs the PoWA GUI. It expects the database to be known by hostname powa-db, as by default in powa-web.conf. The GUI can be accessed on port 8888.

## TO-DO
In no particular order:

* nginx as a reverse proxy with ssl support
* extensible powa-web configuration

