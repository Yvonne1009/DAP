# Java语言基础 类的结构：属性和方法
在Java中，類的結構主要由屬性和方法組成。這兩者是類的核心要素，定義了類的狀態和行為。
1. 屬性（Properties）
屬性，也稱為字段（Field）或成員變量（Member Variables），是用來描述類的狀態或特徵的變量。每個屬性都有自己的數據類型，並可以在類中初始化。屬性通常使用private修飾符來保護數據的封裝性，使得外部無法直接訪問，而是通過公共方法（如getter和setter）來操作。

屬性的特點：
- 封裝性：通常將屬性設為private，以保護數據不被外部直接修改。
- 數據類型：屬性可以是基本數據類型（如int、double、boolean等），也可以是對象類型（如String、ArrayList等）。
- 初始值：屬性可以在聲明時給定初始值，也可以在構造方法中初始化。

範例：
```java
class Car {
    private String brand;  // 車輛品牌
    private String model;  // 車輛型號
    private int year;      // 出廠年份

    // 構造方法
    public Car(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    // Getter方法
    public String getBrand() {
        return brand;
    }

    public String getModel() {
        return model;
    }

    public int getYear() {
        return year;
    }

    // Setter方法
    public void setBrand(String brand) {
        this.brand = brand;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setYear(int year) {
        this.year = year;
    }
}
```
在這個範例中，Car類具有三個屬性：brand（品牌）、model（型號）和year（年份）。這些屬性被定義為private，並通過公共的getter和setter方法來訪問和修改。

2. 方法（Methods）
方法是定義在類中的函數，用來描述類的行為或操作。方法可以訪問和修改類的屬性，並能夠接收參數和返回結果。方法可以是公共的（public）、私有的（private）或受保護的（protected），以控制其訪問範圍。

方法的特點：
- 訪問修飾符：方法的訪問修飾符決定了方法能被哪個範圍的代碼調用。最常見的修飾符是public和private。
- 返回類型：方法可以有返回值（如int、String），也可以沒有返回值，這時候返回類型是void。
- 參數：方法可以接受零個或多個參數，參數用於方法內部的計算或操作。
- 方法體：方法的具體實現部分，包括邏輯操作、計算和對屬性的訪問。

範例：
```java
class Car {
    private String brand;
    private String model;
    private int year;

    // 構造方法
    public Car(String brand, String model, int year) {
        this.brand = brand;
        this.model = model;
        this.year = year;
    }

    // 方法：顯示車輛信息
    public void displayInfo() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }

    // 方法：計算車輛的年齡
    public int calculateAge(int currentYear) {
        return currentYear - year;
    }
}
```
在這個範例中，Car類包含兩個方法：displayInfo和calculateAge。displayInfo方法顯示車輛的信息，沒有返回值（void）；calculateAge方法計算車輛的年齡，並返回一個整數。

3. 屬性與方法的關係
- 屬性代表類的狀態（數據），而方法代表類的行為（操作）。方法通常會訪問和操作屬性，以實現類的功能。
- 封裝性：屬性通常設為私有（private），以保護數據的完整性，而方法可以是公共的（public），用來提供對外的操作介面。
- 互動性：方法可以通過參數和返回值與外部進行數據交換，並通過操作屬性來影響類的狀態。

###### 總結
在Java中，類的結構由屬性和方法組成。屬性定義了類的狀態，而方法定義了類的行為。通過封裝屬性和公開方法，Java實現了數據隱藏和操作介面分離的設計原則，這是面向對象編程的重要特性。理解屬性和方法的結構與關係，是掌握Java類設計的關鍵。