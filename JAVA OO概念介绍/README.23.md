# Java语言基础 四种权限修饰的测试

在Java中，四种权限修饰符（public、protected、default、private）对类、方法和属性的访问权限有不同的影响。以下是对这四种权限修饰符进行测试的代码示例，帮助你理解它们的工作原理和应用场景。

1. 测试public修饰符

public修饰的成员可以在任何地方访问，包括不同的包。

代码示例：

包package1中的类ClassA：
```java
package package1;

public class ClassA {
    public int publicVar = 10;

    public void publicMethod() {
        System.out.println("Public method in ClassA");
    }
}
```
包package2中的类ClassB：
```java
package package2;

import package1.ClassA;

public class ClassB {
    public static void main(String[] args) {
        ClassA a = new ClassA();
        System.out.println(a.publicVar);  // 可访问
        a.publicMethod();  // 可访问
    }
}
```
在这个示例中，ClassB在不同的包中，可以访问ClassA的publicVar和publicMethod。

2. 测试protected修饰符

protected修饰的成员在同一包内和不同包中的子类中是可访问的，但在其他包中的非子类中不可访问。

代码示例：

包package1中的类ClassA：
```java
package package1;

public class ClassA {
    protected int protectedVar = 20;

    protected void protectedMethod() {
        System.out.println("Protected method in ClassA");
    }
}
```
包package2中的类ClassB（子类）：
```java
package package2;

import package1.ClassA;

public class ClassB extends ClassA {
    public void accessProtected() {
        System.out.println(protectedVar);  // 可访问
        protectedMethod();  // 可访问
    }

    public static void main(String[] args) {
        ClassB b = new ClassB();
        b.accessProtected();  // 输出: 20 和 "Protected method in ClassA"
    }
}
```
在这个示例中，ClassB继承自ClassA，可以访问protectedVar和protectedMethod，即使它们位于不同的包中。

3. 测试default（包访问权限）修饰符

default修饰的成员只能在同一个包内访问，在包外无法访问。

代码示例：

包package1中的类ClassA：
```java
package package1;

class ClassA {
    int defaultVar = 30;

    void defaultMethod() {
        System.out.println("Default method in ClassA");
    }
}
```
包package1中的类ClassB：
```java
package package1;

public class ClassB {
    public static void main(String[] args) {
        ClassA a = new ClassA();
        System.out.println(a.defaultVar);  // 可访问
        a.defaultMethod();  // 可访问
    }
}
```
包package2中的类ClassC：
```java
package package2;

import package1.ClassA;

public class ClassC {
    public static void main(String[] args) {
        // ClassA a = new ClassA();
        // System.out.println(a.defaultVar);  // 不可访问，编译错误
        // a.defaultMethod();  // 不可访问，编译错误
    }
}
```
在这个示例中，ClassA中的defaultVar和defaultMethod只能在package1包内访问，package2中的ClassC无法访问它们。

4. 测试private修饰符

private修饰的成员只能在其所属的类内部访问，其他类无论在同一个包还是不同的包中都无法访问。

代码示例：

包package1中的类ClassA：
```java
package package1;

public class ClassA {
    private int privateVar = 40;

    private void privateMethod() {
        System.out.println("Private method in ClassA");
    }

    public void accessPrivate() {
        System.out.println(privateVar);  // 可访问
        privateMethod();  // 可访问
    }
}
```
包package1中的类ClassB：
```java
package package1;

public class ClassB {
    public static void main(String[] args) {
        ClassA a = new ClassA();
        // System.out.println(a.privateVar);  // 不可访问，编译错误
        // a.privateMethod();  // 不可访问，编译错误
        a.accessPrivate();  // 可访问，通过类内的公共方法间接访问私有成员
    }
}
```
在这个示例中，ClassB无法直接访问ClassA的privateVar和privateMethod，但可以通过ClassA的accessPrivate方法间接访问它们。

###### 总结
- public：全局可访问，无论是同包还是跨包。
- protected：在同包内和不同包的子类中可访问，但不能在不同包的非子类中访问。
- default（包访问权限）：仅在同一包内可访问，跨包不可访问。
- private：只能在类内部访问，其他地方不可访问。
通过这些测试代码，你可以更好地理解Java中的四种权限修饰符的作用和适用范围。这些权限修饰符帮助你控制类的成员在应用程序中的可见性，从而提高代码的封装性和安全性。