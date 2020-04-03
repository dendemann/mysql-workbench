# MySQL Workbench

Copyright (c) 2007, 2020, Oracle and/or its affiliates. All rights reserved.

This is a release of [MySQL Workbench](https://mysqlworkbench.org), a graphical tool for working with MySQL servers and databases.

![Home screen on Windows](https://dev.mysql.com/doc/workbench/en/images/wb-home-screen-new.png)

License information can be found in the [License](License.txt) file.

This distribution may include materials developed by third parties. 
For license and attribution notices for these materials, please refer to the [License](License.txt) file. 

For more information on MySQL Workbench, visit 
  [http://dev.mysql.com/doc/workbench/en](http://dev.mysql.com/doc/workbench/en)

For additional downloads and the source of MySQL Workbench, visit
  [http://dev.mysql.com/downloads](http://dev.mysql.com/downloads)

MySQL Workbench is brought to you by the MySQL team at Oracle.

# Building on Windows

Various modifications have been made to get this build (at least the x64 debug variant) up and running using vcpkg package manager.

Compiled successfully using Visual Studio Community 2019 and vcpkg 2020.01.

## Packages required:

```
antlr4:x64-windows             4.7.1-3
boost:x64-windows              1.72.0
bzip2:x64-windows              1.0.6-4
cairo:x64-windows              1.16.0-2
curl:x64-windows               7.68.0
dirent:x64-windows             1.23.2
expat:x64-windows              2.2.7
fontconfig:x64-windows         2.12.4-10
freetype:x64-windows           2.10.1-3
gdal:x64-windows               2.4.1-9
geos:x64-windows               3.6.3-3
gettext:x64-windows            0.19-13
glib:x64-windows               2.52.3-14-5
hdf5:x64-windows               1.10.5-9
icu:x64-windows                61.1-8
libevent:x64-windows           2.1.11-4
libffi:x64-windows             3.1-7
libiconv:x64-windows           1.16-1
liblzma:x64-windows            5.2.4-3
libmysql:x64-windows           8.0.4-5
libpng:x64-windows             1.6.37-6
libpq:x64-windows              12.0
libssh:x64-windows             0.9.0
libwebp:x64-windows            1.0.2-8
libxml2:x64-windows            2.9.9-5
libzip:x64-windows             rel-1-5-2--1
lz4:x64-windows                1.9.2
netcdf-c:x64-windows           4.7.3-1
openjpeg:x64-windows           2.3.1-1
openssl-windows:x64-windows    1.1.1d-1
openssl:x64-windows            1.1.1d
pcre:x64-windows               8.41-4
pcre:x86-windows               8.41-4
pixman:x64-windows             0.38.4-1
pixman:x86-windows             0.38.4-1
proj4:x64-windows              6.3.0-1
python2:x64-windows            2.7.15-2
python3:x64-windows            3.7.3
rapidjson:x64-windows          2019-06-28
sqlite3:x64-windows            3.30.1-2
szip:x64-windows               2.1.1-6
vsqlite:x64-windows            0.3.13
xxhash:x64-windows             0.7.0
zlib:x64-windows               1.2.11-5
zlib:x86-windows               1.2.11-5
zstd:x64-windows               1.4.0-1
``` 

- vsqlite is a custom package that can be found [here](https://github.com/dendemann/vcpkg-packages)
- `vcpkg integrate install` must be run to get Visual Studio integration

## Additional dependencies:

The `WB_3DPARTY_PATH` environemnt variable needs to point to a directory path containing the following structure:

```
+---bin
|       antlr-4.7.1-complete.jar
|       mysql.exe
|       mysqldump.exe
|       ogr2ogr.exe
|       ogrinfo.exe
|       
+---debug
|   \---lib
|           HTMLRenderer.dll
|           mysqlcppconn-7-vs14.dll
|           
\---python
    |   python.exe
    |   python27.dll
    |   sqlite3.dll 
    |   
    +---DLLs 
    +---lib 
    \---Libs 
        \---site-packages 
```
Most of the files from this structure can be borrowed from the MySQL Workbench installation folder. 

## Required binaries:

- [ANTLR](https://www.antlr.org/download/antlr-4.7.1-complete.jar)
- [SWIG](https://sourceforge.net/projects/swig/files/swigwin/swigwin-3.0.12/) installation directory should be added to PATH variable

# Overview

[MySQL Workbench](https://mysqlworkbench.org) is a graphical tool for working with MySQL servers and databases. MySQL Workbench fully supports MySQL server versions 5.6 and higher.

MySQL Workbench functionality covers five main topics:

* **SQL Development:** Enables you to create and manage connections to database servers. Along with enabling you to configure connection parameters, MySQL Workbench provides the capability to execute SQL queries on the database connections using the built-in SQL Editor.

* **Data Modeling (Design):** Enables you to create models of your database schema graphically, reverse and forward engineer between a schema and a live database, and edit all aspects of your database using the comprehensive Table Editor. The Table Editor provides easy-to-use facilities for editing Tables, Columns, Indexes, Triggers, Partitioning, Options, Inserts and Privileges, Routines and Views.

* **Server Administration:** Enables you to administer MySQL server instances by administering users, performing backup and recovery, inspecting audit data, viewing database health, and monitoring the MySQL server performance.

* **Data Migration:** Allows you to migrate from Microsoft SQL Server, Microsoft Access, Sybase ASE, SQLite, SQL Anywhere, PostreSQL, and other RDBMS tables, objects and data to MySQL. Migration also supports migrating from earlier versions of MySQL to the latest releases.

* **MySQL Enterprise Support:** Support for Enterprise products such as MySQL Enterprise Backup, MySQL Firewall, and MySQL Audit.

![Performance dashboard](https://dev.mysql.com/doc/workbench/en/images/wb-performance-dashboard.png)

The [code repository on Github](https://github.com/mysql/mysql-workbench) is where we publish a snapshot of our internal repository everytime a new release of the product is published. Use the [MySQL bug system](http://bugs.mysql.com/) to report any issue you have. You can use Github or the MySQL bug system to contribute to the development. File a pull request on Github or a new issue on the MySQL Bug system with your patch and we will take care of it.
