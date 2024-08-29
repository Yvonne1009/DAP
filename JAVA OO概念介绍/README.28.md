# Java语言基础 构造器练习：三角形

在Java中，构造器用于初始化对象的属性。以下是一个关于三角形的构造器练习，帮助你理解如何使用构造器来创建和初始化三角形对象。

练习：创建一个三角形类

1. 创建一个名为Triangle的类，该类包含三个属性：sideA、sideB和sideC，分别表示三角形的三条边。

2. 为Triangle类编写三个构造器：

- 无参构造器：将三条边的默认长度设置为1。
- 有参构造器：接受三个参数，分别为三条边的长度，并将这些值赋给相应的属性。
- 另一个有参构造器：接受一个参数sideLength，将所有三条边的长度都设置为相同的值。

3. 为Triangle类编写一个方法getPerimeter，计算并返回三角形的周长（即三条边的和）。
4. 编写一个displayInfo方法，打印出三角形的三条边的长度以及周长。

代码示例：
```java
public class Triangle {
    // 三角形的三条边
    private double sideA;
    private double sideB;
    private double sideC;

    // 无参构造器，默认将三条边的长度设置为1
    public Triangle() {
        this.sideA = 1.0;
        this.sideB = 1.0;
        this.sideC = 1.0;
    }

    // 有参构造器，接受三条边的长度作为参数
    public Triangle(double sideA, double sideB, double sideC) {
        this.sideA = sideA;
        this.sideB = sideB;
        this.sideC = sideC;
    }

    // 有参构造器，接受一个参数，所有三条边的长度相同
    public Triangle(double sideLength) {
        this.sideA = sideLength;
        this.sideB = sideLength;
        this.sideC = sideLength;
    }

    // 计算并返回三角形的周长
    public double getPerimeter() {
        return sideA + sideB + sideC;
    }

    // 显示三角形的信息，包括三条边的长度和周长
    public void displayInfo() {
        System.out.println("Side A: " + sideA);
        System.out.println("Side B: " + sideB);
        System.out.println("Side C: " + sideC);
        System.out.println("Perimeter: " + getPerimeter());
    }

    // 主方法，用于测试Triangle类
    public static void main(String[] args) {
        // 使用无参构造器创建Triangle对象
        Triangle triangle1 = new Triangle();
        triangle1.displayInfo();

        // 使用有参构造器创建Triangle对象
        Triangle triangle2 = new Triangle(3.0, 4.0, 5.0);
        triangle2.displayInfo();

        // 使用另一个有参构造器创建等边三角形
        Triangle triangle3 = new Triangle(2.5);
        triangle3.displayInfo();
    }
}
```

###### 总结

通过这个练习，你可以学习到如何使用构造器来创建并初始化一个三角形对象。你还学会了如何重载构造器，以便用不同的方式初始化对象。此外，计算三角形的周长并打印出其信息的方法也展示了如何在类中定义实用的方法来操作对象的属性。通过这个练习，你将对Java中的构造器及其使用有更深入的理解。