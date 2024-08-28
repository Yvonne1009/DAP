# Java语言基础 递归方法的使用

在Java中，遞歸是一種在方法中調用自身的方法。遞歸是一種強大的編程技術，尤其適用於解決那些可以被分解為相似子問題的問題。然而，遞歸也需要小心使用，以避免常見的問題，如無限遞歸和棧溢出。

1. 遞歸的基本概念

遞歸方法的結構通常包括兩部分：
- 基礎情況（Base Case）：遞歸的終止條件，當滿足這個條件時，方法將不再調用自身，而是返回結果。
- 遞歸情況（Recursive Case）：方法在這裡調用自身，並逐步接近基礎情況。

2. 遞歸範例

範例1：計算階乘

階乘是一個經典的遞歸問題，定義為n! = n * (n-1) * ... * 1，並且有0! = 1。

```java
public class Factorial {
    // 計算n的階乘
    public static int factorial(int n) {
        // 基礎情況：如果n為0或1，則階乘為1
        if (n == 0 || n == 1) {
            return 1;
        }
        // 遞歸情況：n! = n * (n-1)!
        return n * factorial(n - 1);
    }

    public static void main(String[] args) {
        int result = factorial(5);
        System.out.println("5! = " + result);  // 輸出: 5! = 120
    }
}
```
在這個範例中，factorial方法通過調用自身來計算n的階乘。當n為0或1時，遞歸結束，直接返回1。否則，方法會一直遞歸，直到達到基礎情況。

範例2：計算斐波那契數列

斐波那契數列是一個數學序列，其中每個數字都是前兩個數字的和，定義為F(n) = F(n-1) + F(n-2)，並且有F(0) = 0和F(1) = 1。

```java
public class Fibonacci {
    // 計算斐波那契數列的第n個數字
    public static int fibonacci(int n) {
        // 基礎情況：F(0) = 0, F(1) = 1
        if (n == 0) {
            return 0;
        } else if (n == 1) {
            return 1;
        }
        // 遞歸情況：F(n) = F(n-1) + F(n-2)
        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    public static void main(String[] args) {
        int result = fibonacci(6);
        System.out.println("Fibonacci of 6 = " + result);  // 輸出: Fibonacci of 6 = 8
    }
}
```
在這個範例中，fibonacci方法通過調用自身兩次來計算斐波那契數列的第n個數字。當n為0或1時，遞歸結束，直接返回相應的值。

3. 遞歸的注意事項

- 基礎情況：確保每個遞歸方法都有一個清晰的基礎情況，否則可能會導致無限遞歸，進而引發StackOverflowError。
- 性能問題：遞歸方法如果沒有適當優化，可能會在計算量較大時導致性能問題。這在斐波那契數列的例子中特別明顯，因為每次計算會重複計算很多次相同的子問題。這可以通過使用動態規劃或記憶化（Memoization）技術來解決。

範例：使用記憶化優化斐波那契數列
```java
import java.util.HashMap;

public class FibonacciMemoized {
    private static HashMap<Integer, Integer> memo = new HashMap<>();

    public static int fibonacci(int n) {
        if (n == 0) {
            return 0;
        } else if (n == 1) {
            return 1;
        }
        
        if (memo.containsKey(n)) {
            return memo.get(n);
        }
        
        int result = fibonacci(n - 1) + fibonacci(n - 2);
        memo.put(n, result);
        return result;
    }

    public static void main(String[] args) {
        int result = fibonacci(6);
        System.out.println("Fibonacci of 6 = " + result);  // 輸出: Fibonacci of 6 = 8
    }
}
```
這個範例通過記憶化技術，將已計算過的斐波那契數字存儲起來，避免重複計算。

4. 遞歸的應用場景

遞歸在許多算法中非常有用，特別是在解決以下問題時：

- 樹結構遍歷：如二叉樹的遍歷、查找等。
- 分治算法：如快速排序、歸併排序等。
- 圖算法：如深度優先搜索（DFS）。
- 數學問題：如階乘、斐波那契數列、組合數計算等。

###### 總結

遞歸方法是Java中處理問題的一種強大工具，特別適用於可以分解為相似子問題的問題。理解遞歸的工作原理、正確設置基礎情況以及避免常見的遞歸陷阱，能夠幫助開發者有效地利用遞歸解決複雜問題。同時，對於可能存在性能問題的遞歸算法，適當的優化如記憶化也是非常重要的。