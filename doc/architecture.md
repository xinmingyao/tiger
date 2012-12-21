architecture picture:    
------------------------------------------------------------------------------------------------------------------------ 	       	       	       	    
       	       	       	       	       	       	      		    
  			  	       	+-----------------------+   
  			  	       	|             	    	|   
  			  	      	|       client	    	|   
     		       	       	       	+-----------+-----+-----+
       	       	       	       	       	      	    |  	  |
     		   	  	       	  redis	    |  	  | memcahced  
       	       	       	       	       	  protocol  |  	  | protocol 
      		   	  	       	       	    |	  |	 
      		   	  			    v	  v	 
      	+-----------------+ 		   +-------------------+             	      +-------------------+
      	|             	  | <----req-------|                   | --------req--------> |                   |
      	|             	  | 	           |           	       |  	    	      |                   |
      	|                 | 	           |                   |       	      	      |                   |
      	|    follow       |------ack------>|      leader       |<--------ack--------- |    follow         |
      	|                 | 	       	   |                   | 	      	      |                   |
      	|                 |                |                   | 	              |                   |
      	|                 | <----commit----|                   |--------commit------> |                   |
      	+-----------------+		   +-------------------+         	      +-------------------+
      								 
      								 
      								 
												  
												  
design:
--------
* [zab protocol](http://research.yahoo.com/pub/3514)
* leveldb

	zab log

	backend storage
* redis
	backend storage,use erlang nif call redis
* client protocol

     memcached protocol

     redis protocol
	
