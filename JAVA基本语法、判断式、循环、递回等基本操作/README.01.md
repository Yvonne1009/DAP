# JAVA基本语法、判断式、循环、递回等基本操作
在Java中，基本語法、判斷式、循環、遞迴等是構成程序的核心操作。以下是對這些基本操作的介紹及範例。

1. 基本語法

Java的基本語法包括類、方法、變量、數據類型等。

例子：基本類結構
```java
public class Example {
    // 屬性（變量）
    int number;
    String text;

    // 方法
    public void printMessage() {
        System.out.println("Hello, World!");
    }

    // 主方法，程序執行的入口
    public static void main(String[] args) {
        Example example = new Example();
        example.printMessage();
    }
}
```
2. 判斷式（條件語句）

Java中常用的判斷式包括if、else if、else以及switch。

例子：if-else語句
```java
public class ConditionExample {
    public static void main(String[] args) {
        int number = 10;

        if (number > 0) {
            System.out.println("Number is positive.");
        } else if (number < 0) {
            System.out.println("Number is negative.");
        } else {
            System.out.println("Number is zero.");
        }
    }
}
```

例子：switch語句
```java
public class SwitchExample {
    public static void main(String[] args) {
        int day = 3;
        String dayName;

        switch (day) {
            case 1:
                dayName = "Monday";
                break;
            case 2:
                dayName = "Tuesday";
                break;
            case 3:
                dayName = "Wednesday";
                break;
            case 4:
                dayName = "Thursday";
                break;
            case 5:
                dayName = "Friday";
                break;
            case 6:
                dayName = "Saturday";
                break;
            case 7:
                dayName = "Sunday";
                break;
            default:
                dayName = "Invalid day";
                break;
        }

        System.out.println("Day: " + dayName);
    }
}
```
3. 循環

Java中的循環語句有for、while和do-while。

例子：for循環
```java
public class ForLoopExample {
    public static void main(String[] args) {
        for (int i = 0; i < 5; i++) {
            System.out.println("i = " + i);
        }
    }
}
```
例子：while循環
```java
public class WhileLoopExample {
    public static void main(String[] args) {
        int i = 0;
        while (i < 5) {
            System.out.println("i = " + i);
            i++;
        }
    }
}
```
例子：do-while循環
```java
public class DoWhileExample {
    public static void main(String[] args) {
        int i = 0;
        do {
            System.out.println("i = " + i);
            i++;
        } while (i < 5);
    }
}
```
4. 遞迴

遞迴是在方法中調用自身的一種技術，常用於解決可以被分解為相似子問題的問題。

例子：遞迴計算階乘
```java
public class RecursionExample {
    // 計算n的階乘
    public static int factorial(int n) {
        if (n == 0) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }

    public static void main(String[] args) {
        int result = factorial(5);
        System.out.println("Factorial of 5 is " + result);
    }
}
```
5. 數組（Array）

數組是一種用於存儲固定大小的相同數據類型元素的容器。

例子：宣告和使用數組
```java
public class ArrayExample {
    public static void main(String[] args) {
        // 宣告並初始化一個整數數組
        int[] numbers = {1, 2, 3, 4, 5};

        // 訪問數組元素
        System.out.println("First element: " + numbers[0]);

        // 遍歷數組
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }
    }
}
```
6. 字符串（String）

字符串在Java中是用於表示文字序列的對象。字符串是不可變的，這意味著一旦創建，字符串的值就無法改變。

例子：字符串操作
```java
public class StringExample {
    public static void main(String[] args) {
        String greeting = "Hello, World!";
        
        // 取得字符串長度
        System.out.println("Length: " + greeting.length());

        // 字符串拼接
        String fullGreeting = greeting + " Have a nice day!";
        System.out.println(fullGreeting);

        // 字符串比較
        boolean isEqual = greeting.equals("Hello, World!");
        System.out.println("Strings are equal: " + isEqual);
    }
}
```
7. 集合框架（Collections Framework）

Java集合框架提供了一組用於存儲和操作數據的類，如ArrayList、HashMap、HashSet等。

例子：使用ArrayList
```java
import java.util.ArrayList;

public class ArrayListExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        // 添加元素
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");

        // 取得大小
        System.out.println("Size: " + list.size());

        // 遍歷列表
        for (String fruit : list) {
            System.out.println(fruit);
        }
    }
}
```
8. 例外處理（Exception Handling）

例外處理用於處理程序中的錯誤或異常情況，避免程序崩潰。

例子：使用try-catch塊
```java
public class ExceptionExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // 這會引發一個異常
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero.");
        }
    }
}
```
9. 文件操作（File Handling）

Java提供了多種方式來讀寫文件，包括使用File類、FileReader、FileWriter、BufferedReader等。

例子：讀取文件
```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class FileReadingExample {
    public static void main(String[] args) {
        try (BufferedReader reader = new BufferedReader(new FileReader("example.txt"))) {
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
10. 面向對象編程（OOP）

Java是一種面向對象的編程語言，這意味著它強調通過類和對象來構建程序。

例子：繼承
```java
public class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

public class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }

    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // 輸出: Dog barks
    }
}
```
###### 總結
除了基本語法、判斷式、循環和遞迴之外，Java還有許多重要的概念，如數組、字符串、集合框架、例外處理、文件操作和面向對象編程等。這些概念和操作構成了Java編程的基礎，理解並掌握它們將使你能夠編寫更加豐富和複雜的應用程序。Java的功能非常強大，這些基礎概念只是開始，還有很多進階主題可以探索。