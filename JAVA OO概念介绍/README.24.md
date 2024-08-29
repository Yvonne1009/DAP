# Java语言基础 封装性练习：基本使用

在Java中，封裝性是面向對象編程的基本概念之一。封裝性指的是將對象的數據（屬性）和操作數據的方法封裝在一起，並隱藏對象的內部實現細節，只對外提供公共的接口。這種做法有助於提高代碼的安全性和可維護性。以下是關於封裝性的基本練習，幫助你理解如何在Java中實現封裝。

1. 使用private關鍵字封裝屬性

在Java中，通常將類的屬性聲明為private，這樣可以保護數據不被外部直接修改。然後，通過公共的getter和setter方法來提供訪問和修改這些屬性的方式。

例子：封裝人的信息
```java
public class Person {
    // 將屬性設為私有，禁止外部直接訪問
    private String name;
    private int age;

    // 提供公共的getter方法以獲取屬性的值
    public String getName() {
        return name;
    }

    // 提供公共的setter方法以設置屬性的值
    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        // 可以在setter方法中添加邏輯，如年齡不能為負數
        if (age >= 0) {
            this.age = age;
        } else {
            System.out.println("Age cannot be negative.");
        }
    }
}
```
在這個範例中，Person類的屬性name和age是私有的，這意味著外部的類無法直接訪問或修改它們。相反，外部類必須通過getName()和setName()等公共方法來獲取和設置這些屬性。

2. 使用封裝的類

現在，我們來看看如何在其他類中使用封裝的Person類。

例子：使用Person類
```java
public class Main {
    public static void main(String[] args) {
        Person person = new Person();

        // 使用setter方法設置屬性的值
        person.setName("Alice");
        person.setAge(25);

        // 使用getter方法獲取屬性的值
        System.out.println("Name: " + person.getName());
        System.out.println("Age: " + person.getAge());

        // 嘗試設置不合理的年齡值
        person.setAge(-5);  // 輸出: Age cannot be negative.
    }
}
```
在這個範例中，我們創建了一個Person對象，並使用setName()和setAge()方法設置name和age屬性的值。通過getName()和getAge()方法，我們可以獲取這些屬性的值。此外，我們還測試了設置無效年齡值的情況，這會觸發setAge()方法中的邏輯檢查。

3. 封裝性的好處

- 數據保護：封裝可以防止對象的內部狀態被隨意修改，從而提高代碼的安全性。
- 靈活性：通過使用getter和setter方法，我們可以在方法中添加額外的邏輯來控制屬性的設置和訪問。
- 易於維護：由於對象的內部細節對外部不可見，因此可以在不影響其他代碼的情況下修改對象的內部實現。

###### 總結
封裝性是Java面向對象編程中的重要概念之一，通過將屬性設置為私有並提供公共的訪問方法，可以保護對象的內部狀態，並控制屬性的設置和訪問方式。這種做法提高了代碼的安全性、靈活性和可維護性。在實際開發中，封裝性有助於創建更可靠和易於維護的軟件系統。