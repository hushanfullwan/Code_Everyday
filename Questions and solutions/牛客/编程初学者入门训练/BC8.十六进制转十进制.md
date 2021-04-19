# BC8 十六进制转十进制

## 一、题目

- 题目描述：BoBo写了一个十六进制整数ABCDEF，他问KiKi对应的十进制整数是多少。
- 输出描述：十六进制整数ABCDEF对应的十进制整数，所占域宽为15。
- 备注：`printf`可以使用使用格式控制串“%md”输出域宽为m的十进制整数。



## 二、题解

#### 1. 利用`printf`实现自动进制转换

```java
public class Main {
    public static void main(String[] args) {
        System.out.printf("%15d", 0xABCDEF);
    }
}
```

#### 2. 利用`BigInteger`实现进制转换

- 知识点

  - `BigInteger(String val, int radix)`：以指定的`BigInteger`的字符串表示形式转换为`BigInteger`。（`radix`不写默认是十进制）

  - `BigInteger.One/TEN/ZERO`：`BigInteger`的常量：1、10、0。

  - `gcd(BigInteger val)`：返回一个`BigInteger`，其值是`abs(this)`和`abs(val)`的最大公约数。

  - `toString(int radix)`：返回此`BigInteger`的给定基数的字符串表示形式。（`radix`不写默认十进制）

- 代码：

  ```java
  import java.math.BigInteger;
  public class Main {
      public static void main(String[] args) {
          System.out.printf("%15s", new BigInteger("ABCDEF", 16).toString());
      }
  }
  ```

#### 3. `Integer`字符串转换成十进制整数

- 知识点：

  - `Integer.parsent(String s, int radix)`：使用`radix`指定参数，将字符串参数解析为有符号的整数（十进制）。（`radix`没写默认将表示十进制的**字符串**转成有符号十进制**整数**）

- 代码：

  ```java
  public class Main {
      public static void main(String[] args) {
          System.out.printf("%15s", Integer.parseInt("ABCDEF", 16));
      }
  }
  ```
  

#### 4. `Integer`转换字符串为`Integer`对象

##### 1. 使用字符流输出

- 步骤

  1. 先转换成Integer对象再转成字符串对象。
  2. 利用字符输入流增加要求的空白字符
  3. 输出最终字符串

- 代码

  ```java
  public class Main {
      public static void main(String[] args){
          String s = Integer.valueOf("ABCDEF", 16).toString();
          StringBuilder sb = new StringBuilder(15);
          for (int i = 0; i < 15 - s.length(); i++) {
              sb.append(" ");
          }
          sb.append(s);
          System.out.println(sb);
      }
  }
  ```

##### 2. 字符串拼接

- 步骤

  1. 转换成Integer对象再转成字符串对象，打印缺少空白字符
  2. 直接打印字符串

- 代码

  ```java
  public class Main {
      public static void main(String[] args){
          String s = Integer.valueOf("ABCDEF", 16).toString();
          for (int i = 0; i < 15 - s.length(); i++) {
              System.out.print(" ");
          }
          System.out.print(s);
          //System.out.print(Integer.valueOf("ABCDEF", 16)); //也可以这样写，因为打印默认输出toString()方法
      }
  }
  ```