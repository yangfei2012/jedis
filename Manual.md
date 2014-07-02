Jedis架构分析

Client ==> BinaryClient ==> Connection
       -->  Commands
   |
   |
   |
Jedis ==> BinaryJedis --> XXXCommands
      --> YYYCommands
   |
   |
   |
JedisFactory --> PooledObjectFactory<Jedis>
   |
   |
   |
JedisPool ==> Pool