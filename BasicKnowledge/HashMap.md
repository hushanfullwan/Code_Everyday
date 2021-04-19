# HashMap

#### 一、主要使用解题方向

1. 寻找某个数字是否已经存在在Map集合中。

#### 二、相关方法

1. 构造方法

   ```java
   Map<Integer, Integer> map = new HashMap<>()；
   ```

2. 方法

   ```java
   // 判断集合中是否有这个key，有的话返回true，没有则false
   map.containsKey(key);
   
   // 从集合中根据key取出对应的value
   map.get(key);
   
   // 将某个k-v键值对放入集合中
   map.put(key, value);
   
   // 返回集合的大小
   map.size();
   ```