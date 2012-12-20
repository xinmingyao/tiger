Tiger Setup Instructions
------

This document explains how to set up a Tiger cluster.  It assumes that
you have already downloaded and successfully built Tiger.  For help with
those steps, please refer to Tiger/README.md.


Overview
---

This document will attempt to give a description of
the common configuration parameters.


Configuration
---

Configurations are stored in the simple text files vm.args and
app.config.  Initial versions of these files are stored in the
rel/files/ subdirectory of the Tiger source tree.  When a release
is generated, these files are copied to rel/Tiger/etc/.

vm.args
---

The vm.args configuration file sets the parameters passed on the
command line to the Erlang VM.  Lines starting with a '#' are
comments, and are ignored.  The other lines are concatenated and
passed on the command line verbatim.

Two important parameters to configure here are "-name", the name to
give the Erlang node running Tiger, and "-setcookie", the cookie that
all Tiger nodes need to share in order to communicate.

app.config
---

The app.config configuration file is formatted as an Erlang VM config
file.  The syntax is simply:

[
 {AppName, [
            {Option1, Value1},
            {Option2, Value2},
            ...
           ]},
 ...
].

Normally, this will look something like:

 {tiger_core, [
              {master_nodes,['m1@127.0.0.1','m2@127.0.0.1','m3@127.0.0.1']}
             ]},

[

This would set the 'mater_nodes'
options for the 'tiger_core' application


The following parameters can be used in app.config to configure Tiger
behavior. 
tiger core
--------
master_nodes: list

  all nodes of the cluster.use 3 ,5,or7 nodes,the nodes should be connected.

   All nodes should have the same cluster name.

tiger_kv
----------

* memcached

	enable:true or false
	
	port:integer default 11211
	
	ip:string default "127.0.0.1"
	
	db_dir:  path for data storage
        
	gc_by_zab_log_count:int default 1000(when update 1000 times,zab log vill gc,remove old log)

* redis
	
	enable:true or false
	
	port:integer default 11211
	
	ip:string default "127.0.0.1"
	
	snapshot: use defual(the time for redis to dump to disk)
	
	gc:use default(after snapshot,gc the log)
	
	conf: use default(the redis storage engine start configue)
	
	db_dir:path for data storage

zab_engine:
-------------

	proposal_log_dir:path for log

lager:
-------------
	all use default

saal
-------------
	all use default
