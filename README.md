What is nsedit?
===============

nsedit is a DNS editor for [PowerDNS](https://www.powerdns.com/). It is created
to finally replace poweradmin and take DNS editing to what we're used at in
2014. It uses the PowerDNS API to make changes in your zones, so you can use
the backend that you want, no matter what.

What is nsedit4virtualizor?
===============

nsedit4virtualizor is a DNS editor for [PowerDNS](https://www.powerdns.com/) installed
in virtualizor [Virtualizor](https://virtualizor.com/). It is a modified version of
nsedit to be enable full DNS features what is not functional in virtualizor. Users
and privileges used from virtualizor database, user list and his privileges in this
version of nsedit is read only.

Features
========
* Import BIND- or AXFR-style dumps of your existing zones
* Add/remove zones and records
* Clone zones
* Show the DNSsec details of a zone
* Multiple user support (readed from virtualizor, read only)
* Allow logging of all actions in NSEdit, including exporting the log in JSON-format
* [experimental] nsedit API, to create zones from another system

Requirements
============
* A webserver running php
* php PDO with mysql support
* php curl
* php with openssl support
* PowerDNS with the JSON-api enabled. Version 4.1 installed with virtualizor

Installing
==========

* Via Git
    -  Run git clone in the directory where you want to run nsedit from
    : ```git clone https://github.com/bajizs/nsedit4virtualizor.git```

    - Select tag v1.0 or skip this if you want to run from master
    : ```git checkout tags/v1.0```
* Via releases
    - Download the zip-file from [Releases](https://github.com/bajizs/nsedit4virtualizor/releases)

* Copy ```includes/config.inc.php-dist``` to ```includes/config.inc.php``` and edit config.inc.php to your needs.

* Visit http(s)://<url>/nsedit/ and login with your virtualizor admin user (or virtualizor client user)

Have fun ;)

Configuring PowerDNS
====================
Minimal configuration of PowerDNS for supporting nsedit has to include 3 directives:
```
webserver=yes
api=yes
api-key=SomeRandomString
```

Screenshots
===========

![The login screen](screenshots/login.png)
![Master zones](screenshots/master-import-zones.png)
![Slave zones](screenshots/slavezones.png)


