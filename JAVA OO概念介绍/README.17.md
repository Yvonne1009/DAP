# Java语言基础 新特性：可变个数形参的方法
在Java中，方法重載是指在同一個類中，可以有多個方法名稱相同但參數不同的方法。這種技術允許我們根據不同的需求來處理多種類型或數量的輸入。以下是關於方法重載的舉例與判斷練習，這將幫助你更好地理解和掌握這個概念。

舉例：方法重載的範例
範例1：基於參數數量的重載
```java
class Calculator {
    // 方法1：計算兩個整數的和
    int add(int a, int b) {
        return a + b;
    }

    // 方法2：計算三個整數的和
    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```
在這個範例中，add方法被重載了兩次：一次用於計算兩個整數的和，另一個用於計算三個整數的和。

範例2：基於參數類型的重載
```java
class Display {
    // 方法1：顯示整數
    void show(int a) {
        System.out.println("Integer: " + a);
    }

    // 方法2：顯示字符串
    void show(String a) {
        System.out.println("String: " + a);
    }
}
```
在這個範例中，show方法被重載以處理不同類型的參數：一個是整數，另一個是字符串。

範例3：基於參數順序的重載
```java
class Example {
    // 方法1：整數和字符串的順序
    void print(int a, String b) {
        System.out.println("Integer: " + a + ", String: " + b);
    }

    // 方法2：字符串和整數的順序
    void print(String b, int a) {
        System.out.println("String: " + b + ", Integer: " + a);
    }
}
```
在這個範例中，print方法被重載以接受不同的參數順序。

練習：判斷以下是否屬於合法的重載
請根據以下代碼，判斷這些方法是否為合法的重載。

練習1
```java
class Test {
    void compute(int a, double b) {}
    void compute(double b, int a) {}
}
```
判斷：這是合法的重載。雖然這兩個方法的參數數量相同，但參數的順序不同，因此編譯器可以區分這兩個方法。

練習2
```java
class Test {
    void compute(int a) {}
    void compute(int b) {}
}
```
判斷：這不是合法的重載。這兩個方法的參數列表完全相同，僅僅是參數名稱不同，這不構成重載。這樣的代碼會導致編譯錯誤。

練習3
```java
class Test {
    void compute(int a) {}
    int compute(int a, int b) {
        return a + b;
    }
}
```
判斷：這是合法的重載。儘管這兩個方法的名稱相同，但參數列表不同，一個方法有一個參數，另一個方法有兩個參數，因此這是合法的重載。

練習4
```java
class Test {
    void compute(int a, int b) {}
    int compute(int a, int b) {
        return a + b;
    }
}
```
判斷：這不是合法的重載。雖然這兩個方法的返回類型不同，但參數列表完全相同，這樣的代碼會導致編譬錯誤。Java中的重載僅依賴於參數列表，而不考慮返回類型。

###### 總結
在進行方法重載時，必須確保方法的參數列表（參數數量、類型、順序）有所不同。僅僅改變返回類型或參數名稱是不足以構成重載的。通過這些練習，希望你能夠更好地理解如何正確地實現方法重載，以及如何避免常見的錯誤。