# BC9 printf的返回值

## 一、题目

- 题目描述：KiKi写了一个输出`Hello world!`的程序，BoBo老师告诉他`printf`函数有返回值，你能帮他写个程序输出`printf("Hello world!")`的返回值吗？
- 输出描述：
  - 第一行为`Hello world!`
  - 第二行为`printf("Hello world!")`调用后的**返回值**。



## 二、题解

> 注意：此题的`printf`返回值指的是c语言中的返回值，即打印的字符串的长度
>
> Java中的`printf`的返回值是`java.io.PrintStream`对象。

```java
public class Main {
    public static void main(String[] args) {
        String s = "Hello world!";
        System.out.println(s);
        System.out.println(s.length());
    }
}
```