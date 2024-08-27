# Java语言基础 对类和对象创建的再理解
在Java中，類和對象是面向對象編程的核心概念。了解如何創建類和對象是掌握Java編程的基礎。

1. 類的創建
類是一種藍圖或模板，定義了一組對象的公共屬性和行為。在Java中，類使用class關鍵字來定義。類本身不佔用內存，它只是對象的結構定義。

定義類的步驟：
- 定義屬性：屬性（或稱為成員變量）代表類的狀態。
- 定義方法：方法描述類的行為，方法可以操作類的屬性。

範例：
```java
class Car {
    // 屬性
    String brand;
    String model;
    int year;

    // 方法
    void startEngine() {
        System.out.println("The engine is starting...");
    }

    void displayInfo() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }
}
```
在這個範例中，Car類定義了三個屬性：brand（品牌）、model（型號）和year（年份），以及兩個方法：startEngine（啟動引擎）和displayInfo（顯示車輛信息）。

2. 對象的創建
對象是類的實例，是類所描述的具體存在的實體。在Java中，對象是使用new關鍵字來創建的。創建對象時，會調用類的構造方法，並分配內存來儲存對象的屬性和方法。

創建對象的步驟：
- 聲明對象引用變量：定義一個變量來引用創建的對象。
- 使用new關鍵字創建對象：實例化對象，並分配內存。
- 訪問對象的屬性和方法：使用點操作符（.）來訪問對象的屬性和方法。

範例：
```java
public class Main {
    public static void main(String[] args) {
        // 創建Car類的對象
        Car myCar = new Car();

        // 設定對象的屬性值
        myCar.brand = "Toyota";
        myCar.model = "Corolla";
        myCar.year = 2020;

        // 調用對象的方法
        myCar.startEngine();
        myCar.displayInfo();
    }
}
```
在這個範例中：

- Car myCar = new Car(); 這行代碼創建了一個Car類的實例，並將其引用賦值給myCar變量。
- 創建對象後，可以使用myCar.brand、myCar.model和myCar.year來設定或獲取屬性值。
- 可以通過myCar.startEngine()和myCar.displayInfo()來調用對象的方法。

3. 構造方法（Constructor）
構造方法是一種特殊的方法，用於在創建對象時初始化對象的屬性。構造方法的名稱必須與類名相同，並且沒有返回值。當使用new關鍵字創建對象時，構造方法會自動被調用。

範例：
```java
class Car {
    String brand;
    String model;
    int year;

    // 構造方法
    Car(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    void displayInfo() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        // 使用構造方法創建對象並初始化屬性
        Car myCar = new Car("Honda", "Civic", 2018);
        myCar.displayInfo();
    }
}
```
在這個範例中，Car類定義了一個構造方法，用於在創建對象時初始化brand、model和year屬性。創建對象時，直接傳遞參數來設置屬性的初始值。

###### 總結
在Java中，類是對象的模板，定義了對象的屬性和方法。對象是類的實例，代表具體的實體。創建對象時，通過new關鍵字來實例化類，並可以通過構造方法來初始化對象的屬性。理解類和對象的創建過程，是掌握Java面向對象編程的重要步驟。