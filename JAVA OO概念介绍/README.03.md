# Java语言基础 面向对象编程学习的主线
學習面向對象編程（OOP）是Java語言基礎中的核心內容。OOP不僅僅是Java的基石，還是現代軟體開發中的重要編程範式。以下是學習面向對象編程的主線，幫助你系統性地掌握這一概念。
1. 理解對象與類別
- 類別（Class）：類別是對象的藍圖或模板，定義了對象的屬性（變量）和行為（方法）。在Java中，使用class關鍵字來定義類別。
- 對象（Object）：對象是類別的實例，每個對象都有自己的屬性值和方法行為。對象通過new關鍵字創建。
- 範例:
```java
class Dog {
    String name;
    int age;
    
    void bark() {
        System.out.println(name + " is barking!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();  // 創建一個對象
        myDog.name = "Buddy";
        myDog.age = 3;
        myDog.bark();  // 呼叫對象的方法
    }
}
```
2. 掌握封裝（Encapsulation）
- 封裝：封裝是一種隱藏對象的內部實現細節，並僅暴露必要的介面（方法）給外界的技術。這通常通過將變量設為私有（private）並提供公共（public）的方法來訪問和修改這些變量（getter和setter方法）。
- 範例：
```java
class Student {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Student student = new Student();
        student.setName("John");
        student.setAge(20);
        System.out.println("Name: " + student.getName() + ", Age: " + student.getAge());
    }
}
```
3. 理解繼承（Inheritance）
- 繼承：繼承是指一個類別（子類）繼承另一個類別（父類）的屬性和方法，從而實現代碼重用。Java中使用extends關鍵字來實現繼承。繼承關係是is-a的關係。
- 範例：
```java
class Animal {
    void eat() {
        System.out.println("This animal is eating.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("This dog is barking.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat();  // 繼承自Animal
        myDog.bark(); // Dog自己的方法
    }
}
```
4. 探索多型（Polymorphism）
- 多型：多型是指同一個方法可以在不同的類別中有不同的實現。在Java中，多型的實現主要依賴於方法覆寫（Override）和方法重載（Overload）。
- 方法覆寫（Override）：子類可以提供父類方法的具體實現。
- 方法重載（Overload）：同一個類別中可以有多個同名但參數不同的方法。
- 範例：
```java
class Animal {
    void sound() {
        System.out.println("This animal makes a sound.");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("The dog barks.");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("The cat meows.");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        Animal myCat = new Cat();

        myDog.sound(); // The dog barks.
        myCat.sound(); // The cat meows.
    }
}
```
5. 介面與抽象類別（Interface and Abstract Class）
- 介面（Interface）：介面是一種更高層次的抽象，定義了類別應實現的方法而不提供具體實現。類別通過implements關鍵字來實現介面。介面中的所有方法默認為public和abstract。
- 抽象類別（Abstract Class）：抽象類別是不能被實例化的類別，包含一個或多個抽象方法（沒有方法體）。抽象類別通過extends來繼承。
- 範例：
```java
interface AnimalInterface {
    void sound();
}

abstract class Animal {
    abstract void sound();

    void eat() {
        System.out.println("This animal is eating.");
    }
}

class Dog extends Animal implements AnimalInterface {
    @Override
    void sound() {
        System.out.println("The dog barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.sound();  // The dog barks.
        myDog.eat();    // This animal is eating.
    }
}
```
###### 總結
面向對象編程是Java開發的核心。學習這一編程範式的主線應圍繞對象與類別的基本概念開始，逐步深入到封裝、繼承、多型以及介面與抽象類別等更高層次的內容。通過不斷的實踐和綜合應用，可以有效地掌握OOP的精髓，為進一步的Java編程打下堅實的基礎。