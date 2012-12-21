
welcome to Tiger db
=====
-----
Tiger db is a distributed,high avialable,high performance NoSQL data storage system,
* strong consistency
* use redis or memcached protocol(only crud api)
* embeded leveldb as log engine
* embeded leveldb and redis as backend storage
* use zab protocol synchronize data between instance 

wher to find more
-----------

* [architectrue](http://)
Quick Start
----------

* build Tiger db
* start Tiger db cluster
* connect Tiger db use redis client or memcached client
Build Tiger db
---------

* install R15B or above
* cd $Tiger
* make && make devrel
* ./start_cluster

Connect to Tiger db
--------

use redis client or memcached client to connect to Tiger,
only suport get set delete api

Server Management
=======
Configuration
-------

* vm.args
* app.config
* [basic setup](http://github.com/xinmingyao/tiger/blob/dev/doc/basic-setup.md)

Server Control
-----

* bin/tiger --help

test:
-------
  
