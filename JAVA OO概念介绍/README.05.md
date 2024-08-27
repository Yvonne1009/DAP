# Java语言基础 两个要素：类和对象
在Java編程中，類和對象是兩個最基本的要素，它們構成了面向對象編程（OOP）的核心。
1. 類（Class）
類是一種藍圖或模板，用來描述某一類對象的共同屬性和行為。在Java中，類使用class關鍵字來定義。類本身不佔用內存，它僅僅是對象的定義。

特點：
- 屬性（Properties）：又稱為字段（Field）或成員變量（Member Variables），是類中用來描述對象特徵的變量。例如，Student類可能有name和age這樣的屬性。
- 方法（Methods）：是類中用來描述對象行為的函數或操作。例如，Student類可能有study和takeExam這樣的方法。
- 構造方法（Constructor）：是一種特殊的方法，用於在創建對象時初始化對象的屬性。構造方法的名稱與類名相同，並且沒有返回值。

範例：
```java
class Student {
    String name; // 屬性
    int age;     // 屬性

    // 構造方法
    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 方法
    void study() {
        System.out.println(name + " is studying.");
    }

    void takeExam() {
        System.out.println(name + " is taking an exam.");
    }
}
```
在這個範例中，Student類定義了兩個屬性name和age，並提供了兩個方法study和takeExam來描述學生的行為。

2. 對象（Object）
對象是類的實例，是實際存在的個體。在Java中，對象是通過類創建的，並且佔用內存。每個對象都有自己的屬性值，並且可以調用類中的方法來執行某些操作。

特點：
- 實例化：對象的創建過程稱為實例化。通過new關鍵字調用類的構造方法來創建對象。
- 內存佔用：對象在創建時會在內存中佔據空間，用來存儲對象的屬性值。
- 獨立性：每個對象都是獨立的，擁有自己的屬性值，即使它們來自同一個類。

範例：
```java
public class Main {
    public static void main(String[] args) {
        // 創建Student類的對象
        Student student1 = new Student("Alice", 20);
        Student student2 = new Student("Bob", 22);

        // 調用對象的方法
        student1.study();
        student2.takeExam();
    }
}
```
在這個範例中，student1和student2是Student類的兩個實例（對象）。它們各自擁有獨立的name和age屬性，並且可以獨立調用study和takeExam方法。

3. 類與對象的關係
- 類是對象的模板或藍圖，定義了對象的結構和行為。
- 對象是類的實例，代表具體存在的個體。每個對象根據類的定義，具有相同的結構（屬性和方法），但擁有不同的屬性值。
###### 總結
類和對象是Java語言中最基本的要素。類定義了對象的屬性和行為，是一個抽象的概念；而對象則是類的具體實例，代表真實存在的個體。理解這兩個要素及其關係，是學習和掌握Java面向對象編程的關鍵。