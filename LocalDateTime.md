# LocalDateTime的一些用法

<br>

* 获取当前时间

  ```java
  LocalDateTime now = LocalDateTime.now();` 
  ```

  在不少方法里都是直接调用 `LocalDateTime.now()`  

    

* gmt格式的字符串转化为LocalDateTime对象

  ```java
  String thatDay = "2021-5-10T18:01:22";
  LocalDateTime time = LocalDateTime.parse(thatDay);
  ```

    

* 非gmt格式的字符串转化为LocaDateTime对象

  ```java
  String str1 = "2021-05-01 18:00:00";
  DateTimeFormatter dtf =DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
  LocalDateTime time = LocalDateTime.parse(str1,dtf);
  ```

  