 # BC2 我是大V

> 输出描述：
>
> v    v
>   v v 
>     v

1. 直接打印

   ```java
   public class Main {
       public static void main(String[] args) {
           System.out.println("v   V\n v v \n  v");
       }
   }
   ```

2. 循环输出

   ```java
   public class Main {
       public static void main(String[] args) {
           for (int i = 0; i < 3; i++) {
               for (int j = 0; j < 5; j++) {
                   if (i == j || j == 4-i) {
                       System.out.print("v");
                   } else {
                       System.out.print(" ");
                   }
               }
               System.out.print("\n");
           }
       }
   }
   ```