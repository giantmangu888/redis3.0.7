

# redis3.0.7
redis-3.0.7 updates
This is redis-3.0.7 source code,which is updated by guweitao
the updates as follows:
1 process title
When start a redis,the process as follows:

before update:   
 dba       2154      1  0 00:23 ?        00:00:00 /usr/local/redis30/bin/redis-server *:6380
 Under this scene,we do not know the directory of he redis.
  
 after update:   
 dba      18107     1  0 Mar14 ?        00:03:48 redis-server   /data1/redis6910/redis6910.cnf
 Obviously,it prints the absolute directory of the redis conf,which is convenient to operate the redis.
  
  2 Do not modify requirepass & masterauth  by sentinel
  before update:   
  When start redis with sentinels and the master failovers:
  the sentinel will modify the redis.conf,which includes the variables above.In this case,the redis is risky.
  
  after update:   
  when the master failovers,the sentinel will modify the redis.conf,which excludes the variables above.
  
  
  3 load data online   
  The redis does not support to load data online originally
  after update,it can load data online,which includes aof file and rdb file.
  
  127.0.0.1:6910> ? loadaof   
  
    LOADAOF aof filename   
    summary: load aof file online(add by @guweitao)
    since: 3.0.7
    group: server
  
  127.0.0.1:6910> ? loadrdb   
  
    LOADRDB rdb filename   
    summary: load rdb file online,which can not repeat!!!(add by @guweitao)   
    since: 3.0.7   
    group: server   
  
  
  For details,Please view the readme file of the code.   
  
  contact us:   
  qq:422186266   
  email:422186266@qq.com    
