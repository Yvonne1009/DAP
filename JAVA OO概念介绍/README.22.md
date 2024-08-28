# Java语言基础 四种权限修饰的理解

在Java中，權限修飾符（Access Modifiers）決定了類、方法和屬性等成員對於其他類的可訪問性。Java中有四種主要的權限修飾符，它們分別是public、protected、default（也稱為包訪問權限），以及private。這些修飾符控制著成員在不同範圍內的可見性和訪問權限。

1. public（公開訪問）

- 描述：public修飾符表示成員是完全公開的，對於任何其他類別都是可訪問的，無論它們位於同一個包中還是不同包中。
- 應用場景：通常用於類、方法或屬性，需要在整個應用程序中全局可訪問時。

範例：
```java
public class Example {
    public int publicVar = 10;

    public void publicMethod() {
        System.out.println("This is a public method.");
    }
}
```
在這裡，publicVar和publicMethod可以在任何其他類別中直接訪問，無論這些類別位於同一個包還是不同包中。

2. protected（受保護訪問）

- 描述：protected修飾符表示成員對於相同包內的所有類以及不同包中的子類都是可訪問的。但在不同包中的非子類無法訪問受保護的成員。
- 應用場景：當成員需要在繼承鏈中可訪問，但不希望完全公開時使用。
範例：
```java
public class Parent {
    protected int protectedVar = 20;

    protected void protectedMethod() {
        System.out.println("This is a protected method.");
    }
}

class Child extends Parent {
    public void accessProtected() {
        System.out.println(protectedVar);  // 可訪問
        protectedMethod();  // 可訪問
    }
}
```
在這個範例中，protectedVar和protectedMethod對於Parent類所在包中的其他類以及所有子類都是可訪問的。

3. default（默認或包訪問權限）

- 描述：如果沒有顯式使用任何權限修飾符，則成員具有包訪問權限，這意味著它只能在相同包內的其他類中被訪問，包外的類不能訪問它。
- 應用場景：當成員只需要在同一個包內共享，但不應該對包外公開時使用。

範例：
```java
class Example {
    int defaultVar = 30;  // 沒有修飾符，默認為包訪問權限

    void defaultMethod() {
        System.out.println("This is a default method.");
    }
}
```
在這個範例中，defaultVar和defaultMethod只能在相同包內的其他類中被訪問，而在包外則無法訪問。

4. private（私有訪問）

- 描述：private修飾符表示成員僅在其所屬類中可訪問，對於其他任何類，包括子類，都是不可訪問的。
- 應用場景：當成員僅應該在類內部使用，完全封裝時使用。
範例：
```java
public class Example {
    private int privateVar = 40;

    private void privateMethod() {
        System.out.println("This is a private method.");
    }

    public void accessPrivate() {
        System.out.println(privateVar);  // 可訪問
        privateMethod();  // 可訪問
    }
}
```
在這個範例中，privateVar和privateMethod只能在Example類內部訪問，無法在其他類中訪問。

###### 總結
- public：完全公開，任何地方都能訪問。
- protected：包內可訪問，包外的子類可訪問。
- default（無修飾符）：包內可訪問，包外不可訪問。
- private：僅在類內可訪問，其他任何地方都不可訪問。

理解這些權限修飾符的作用及適用範圍，有助於設計更安全、更結構化的Java應用程序。根據具體需求選擇合適的權限修飾符，可以有效地控制代碼的可訪問性，實現數據封裝和保護。