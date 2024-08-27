# Java语言基础 图形化界面操作与命令行操作介绍
在Java編程中，操作界面可以分為兩種主要方式：圖形化界面操作（GUI，Graphical User Interface） 和 命令行操作（CLI，Command Line Interface）。以下是對這兩種操作方式的介紹。
###### 圖形化界面操作（GUI）
Java中主要通過 Swing 和 JavaFX 來實現圖形化界面操作。
1. Swing
- Swing 是Java標準庫中的一部分，用於構建圖形化用戶界面。它提供了豐富的組件如按鈕（JButton）、文本框（JTextField）、標籤（JLabel）、面板（JPanel）等，可以用來創建複雜的桌面應用程式。
- 基本組件：
    - JFrame：主窗口，用於容納其他組件。
    - JButton：按鈕，用於觸發操作事件。
    - JLabel：標籤，用於顯示文本或圖像。
    - JTextField：文本框，用於接收用戶輸入。
- 事件處理：Swing中通過事件監聽器來處理用戶的交互，如按鈕點擊、鼠標點擊等。常見的事件處理方法包括ActionListener（處理按鈕點擊事件）和MouseListener（處理鼠標事件）。
- 佈局管理：Swing提供了多種佈局管理器，如BorderLayout、FlowLayout、GridLayout等，用於控制組件在窗口中的排列方式。
範例：建立一個簡單的Swing應用程式，包含一個按鈕和一個標籤，點擊按鈕後標籤文本會發生變化。
```java
    import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class SimpleSwingApp {
    public static void main(String[] args) {
        JFrame frame = new JFrame("簡單的Swing應用");
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        JLabel label = new JLabel("按下按鈕");
        JButton button = new JButton("點我");

        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                label.setText("按鈕已點擊！");
            }
        });

        frame.getContentPane().add(label, "North");
        frame.getContentPane().add(button, "South");

        frame.setVisible(true);
    }
}

 ```
2. JavaFX
- JavaFX 是一個較新的GUI框架，提供了更現代的界面設計和更靈活的布局選項。JavaFX還支持動畫、CSS樣式和媒體播放等更高級的功能。
- 基本組件：
    - Stage：應用程式的主窗口。
    - Scene：舞台上的場景，包含所有UI元素。
    - Button：按鈕，類似Swing中的JButton。
    - Label：標籤，類似Swing中的JLabel。
- 佈局：JavaFX提供了多種佈局，如VBox、HBox、GridPane等，支持更加靈活的UI排列方式。
- 事件處理：JavaFX使用事件驅動模型來處理用戶的操作，通常通過Lambda表達式來簡化事件處理。
範例：建立一個簡單的JavaFX應用程式，包含一個按鈕和一個標籤，點擊按鈕後標籤文本會發生變化。
```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;

public class SimpleJavaFXApp extends Application {
    @Override
    public void start(Stage primaryStage) {
        Label label = new Label("按下按鈕");
        Button button = new Button("點我");

        button.setOnAction(e -> label.setText("按鈕已點擊！"));

        VBox vbox = new VBox(label, button);
        Scene scene = new Scene(vbox, 300, 200);

        primaryStage.setTitle("簡單的JavaFX應用");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}

```
###### 命令行操作（CLI）
命令行操作是指用戶通過命令行（如終端或命令提示符）來與應用程式進行交互。Java應用可以通過System.out.println()來輸出信息，通過Scanner類來獲取用戶輸入。
1. 輸出信息
- 使用System.out.println()可以在命令行中打印信息。例如：
```java
    public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```
當運行這個程序時，會在命令行中顯示 "Hello, World!"。

2. 獲取用戶輸入
- Java中可以使用Scanner類來從命令行讀取用戶的輸入。例如：
```java
    import java.util.Scanner;

public class UserInput {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("請輸入你的名字：");
        String name = scanner.nextLine();
        System.out.println("你好, " + name + "!");
    }
}
```
當運行這個程序時，用戶可以在命令行中輸入名字，程序會讀取並顯示一個問候語。

3. 處理命令行參數
- Java程序可以接收命令行參數，這些參數會作為main方法的args數組傳入。例如：
```java
    public class CommandLineArgs {
    public static void main(String[] args) {
        if (args.length > 0) {
            System.out.println("你提供了以下參數：");
            for (String arg : args) {
                System.out.println(arg);
            }
        } else {
            System.out.println("你沒有提供任何參數。");
        }
    }
}
```
當運行這個程序時，可以通過命令行傳遞參數，程序會列出所有參數。

###### 總結
圖形化界面操作（GUI）和命令行操作（CLI）是Java應用程式中兩種不同的交互方式。GUI適合需要豐富用戶界面和交互的應用，而CLI則更適合需要簡單、高效操作的應用，如腳本工具或後端服務。在實際開發中，根據應用的需求選擇適合的交互方式，並合理運用Java中的API，可以有效提高程序的可用性和用戶體驗。