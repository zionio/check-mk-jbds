[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://opensource.org/licenses/MIT)

Check_MK JBDS 
==============

Description
-----------

Simple Check_MK local check to monitor JBoss datasources statistics

Tested on:
* JBoss AS 7.1.0
* JBoss AS 7.1.1
* JBoss AS 7.1.3
* JBoss EAP 6.4

Support:
* standalone
* standalone with multiple instances
* domain

Setup
-----
Get agent directories

```bash
$ /path/to/check_mk_agent | grep Directory
AgentDirectory: /etc/check-mk-agent
DataDirectory: /var/lib/check_mk_agent
SpoolDirectory: /var/lib/check_mk_agent/spool
PluginsDirectory: /usr/share/check-mk-agent/plugins
LocalDirectory: /usr/share/check-mk-agent/local
```

Copy 
* `mk_jbds` in **LocalDirectory**
* `mk_jbds.cfg` in **AgentDirectory**

then discovery new services...

Configuration file
------------------

Edit `mk_jbds.cfg` for every *instances*:

* username: used to connect to jboss management web console
* password: cleartext user password 
* host: hostname/ip of the jboss management web console
* port: port of the jboss management web console
* realm: ManagementRealm
* protocol: http
* stats: for every needed statistics you can set upper and lower value for WARN and CRIT alerts 

