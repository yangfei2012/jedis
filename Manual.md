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



关于Protocol, RedisInputStream，　RedisOutputStream
由于采用符合Redis的Socket协议通信，所以这里
采用自定义的Stream（继承filter）从而可以进行符合Redis协议的流操作。(逐字符进行redis协议操作)
RedisInputStream ==> FilterInputStream
RedisOutputStream ==> FilterOutputStream

