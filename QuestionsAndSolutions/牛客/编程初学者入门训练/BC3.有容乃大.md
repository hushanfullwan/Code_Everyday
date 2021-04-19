# BC3 有容乃大

输出描述：

> 不同整型数据类型在内存中占多大（字节），具体格式详见输出样例，输出样例中的?为不同整型数据类型在内存中占的字节数。输出样例如下：
> The size of short is ? bytes.
> The size of int is ? bytes.
> The size of long is ? bytes.
> The size of long long is ? bytes.

1. 知识点：

   1. 求数据类型字节大小时，要用`包装类型.SIZE/8`。
   2. `包装类型.SIZE`表示的是所占空间的大小即所占`位`大小，而`字节`大小为`位大小/8`。

2. 求解代码，纯打印

   ```java
   public class Main {
       public static void main(String[] args) {
           System.out.println("The size of short is " + Short.SIZE/8 + " bytes.");
           System.out.println("The size of int is " + Integer.SIZE/8 + " bytes.");
           System.out.println("The size of long is " + Long.SIZE/8 + " bytes.");
           System.out.println("The size of long long is " + Long.SIZE/8 + " bytes.");
       }
   }
   ```