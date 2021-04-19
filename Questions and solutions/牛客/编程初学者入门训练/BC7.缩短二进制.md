# BC7 缩短二进制

## 一、题目

- 题目描述：我们处理的整数通常用十进制表示，在计算机内存中是以二进制补码形式存储，但通常二进制表示的整数比较长，为了便于在程序设计过程中理解和处理数据，通常采用八进制和十六[进制](https://www.baidu.com/s?wd=16进制&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)，缩短了[二进制补码表示的整数](https://www.baidu.com/s?wd=二进制数&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)，但保持了[二进制数](https://www.baidu.com/s?wd=二进制数&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)的表达特点。请输出十进制整数1234对应的八进制和十六进制。
- 输出描述：十进制整数1234对应的八进制和十六进制（字母大写），用空格分开，并且要求，在八进制前显示前导0，在十六进制数前显示前导0X。
- 备注：`printf`可以使用使用格式控制串“%o”、“%X”分别输出八进制整数和十六进制整数，并使用修饰符“#”控制前导显示



## 二、题解

#### 1. 利用`printf`实现进制转换

- 知识点

  - **%d**表示以**十进制整数**形式输出

  - **%o**表示以**八进制**形式输出

  - **%x**表示以**十六进制**形式输出

  - **%X**表示以**十六进制**形式输出，并且将字母（A、B、C、D、E、F）换成大写

  - **%e**表示以**科学记数法**输出浮点数

  - **%E**表示以**科学记数法**形式输出浮点数，而且将`e`大写

  - **%f**表示以**十进制浮点数**形式输出，在**%f**之间加上`x.n`表示输出浮点数共x位，输出时保留小数点后n位

    ```java
    public class Main {
        public static void main(String[] args) {
            System.out.printf("0" + "%o", 1234);
            System.out.printf(" 0X" + "%X", 1234);
        }
    }
    ```

#### 2. 利用`Integer`实现进制转换

- 知识点
  - `Integer.toOctalString(int i)`：以八进制无符号整数形式返回一个整数参数的字符串表示形式。
  - `Integer.toHexString(int i)`：以十六进制无符号整数形式返回一个整数参数的符号串表示形式。
  - `public String toUpperCase()`：使用默认语言环境的规则将此 String 中的所有字符都转换为**大写**。此方法等效于`toUpperCase(Locale.getDefault())`。 
  - **小写**是`toLowerCase()`。

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("0" + Integer.toOctalString(1234) + 
                           " 0X" + Integer.toHexString(1234).toUpperCase());
    }
}
```