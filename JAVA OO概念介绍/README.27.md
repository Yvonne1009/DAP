# Java语言基础 构造器练习：基本使用

在Java中，構造器是用來創建對象並初始化對象屬性的一種特殊方法。通過練習構造器的基本使用，你可以更好地理解如何在Java中使用構造器來創建和初始化對象。以下是一些構造器的基本練習。

1. 練習：創建無參構造器

創建一個類Dog，該類包含兩個屬性：name（狗的名字）和age（狗的年齡）。首先，為這個類創建一個無參構造器，並在構造器內部將name設置為"Unknown"，將age設置為0。

代碼範例：
```java
public class Dog {
    String name;
    int age;

    // 無參構造器
    public Dog() {
        this.name = "Unknown";
        this.age = 0;
    }

    // 顯示狗的信息
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        // 使用無參構造器創建Dog對象
        Dog dog = new Dog();
        dog.displayInfo();  // 輸出: Name: Unknown, Age: 0
    }
}
```
2. 練習：創建有參構造器

在Dog類中，添加一個有參構造器，該構造器接受兩個參數：name和age，並使用這些參數來初始化對應的屬性。

代碼範例：
```java
public class Dog {
    String name;
    int age;

    // 有參構造器
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 顯示狗的信息
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        // 使用有參構造器創建Dog對象
        Dog dog = new Dog("Buddy", 3);
        dog.displayInfo();  // 輸出: Name: Buddy, Age: 3
    }
}
```
3. 練習：構造器重載

為Dog類添加一個構造器重載。除了前面定義的構造器之外，添加一個只接受name參數的構造器，並將age設置為默認值1。

代碼範例：
```java
public class Dog {
    String name;
    int age;

    // 無參構造器
    public Dog() {
        this.name = "Unknown";
        this.age = 0;
    }

    // 有參構造器
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 構造器重載，只接受name參數
    public Dog(String name) {
        this.name = name;
        this.age = 1;  // 默認年齡為1
    }

    // 顯示狗的信息
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        // 使用構造器重載創建Dog對象
        Dog dog1 = new Dog("Buddy");
        dog1.displayInfo();  // 輸出: Name: Buddy, Age: 1

        Dog dog2 = new Dog("Max", 5);
        dog2.displayInfo();  // 輸出: Name: Max, Age: 5
    }
}
```
4. 練習：使用this()調用另一個構造器

修改Dog類的構造器，使得無參構造器能夠調用只接受name參數的構造器，並將name設置為"Unknown"。

代碼範例：
```java
public class Dog {
    String name;
    int age;

    // 無參構造器
    public Dog() {
        this("Unknown");  // 調用只接受name參數的構造器
    }

    // 有參構造器
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 構造器重載，只接受name參數
    public Dog(String name) {
        this.name = name;
        this.age = 1;  // 默認年齡為1
    }

    // 顯示狗的信息
    public void displayInfo() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        // 使用無參構造器創建Dog對象
        Dog dog = new Dog();
        dog.displayInfo();  // 輸出: Name: Unknown, Age: 1
    }
}
```
###### 總結

通過這些練習，你可以更好地理解如何在Java中使用構造器來創建和初始化對象。構造器允許你靈活地設置對象的初始狀態，並通過構造器重載和this()方法來簡化代碼，避免重複。熟練掌握構造器的使用是編寫清晰、可維護代碼的基礎。