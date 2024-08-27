# Java语言基础 常用的命令行指令
在使用Java進行開發時，經常需要與操作系統的命令行（在Windows系統中稱為DOS命令行）進行互動。以下是一些常用的DOS命令行指令，這些指令在Java開發過程中非常有用。
###### 常用DOS命令行指令
1. cd（Change Directory）：
- 作用：切換當前工作目錄。
- 用法：
    - cd [目錄路徑]：切換到指定目錄。
    - cd ..：返回到上一層目錄。
    - cd \：切換到根目錄。
- 範例：
```shell
cd C:\Users\YourUsername\Documents
cd ..
cd \
```
2. dir（Directory）：
- 作用：列出當前目錄中的文件和文件夾。
- 用法：
    - dir：列出當前目錄的內容。
    - dir /p：分頁顯示內容。
    - dir /w：寬顯示格式，每行顯示多個文件或文件夾名稱。
- 範例：
```shell
dir
dir /p
dir /w
```
3. cls（Clear Screen）：
- 作用：清除命令提示符窗口中的所有內容。
- 用法：
    - cls：清屏。
- 範例：
```shell
cls
```
4. mkdir（Make Directory） 或 md：
- 作用：創建一個新的文件夾。
- 用法：
    - mkdir [文件夾名稱]：在當前目錄下創建一個新文件夾。
- 範例：
```shell
mkdir newFolder
```
5. rmdir（Remove Directory） 或 rd：
- 作用：刪除一個文件夾。
- 用法：
    - rmdir [文件夾名稱]：刪除指定的空文件夾。
    - rmdir /s [文件夾名稱]：刪除指定的文件夾及其所有子文件夾和文件。
- 範例：
```shell
rmdir emptyFolder
rmdir /s oldFolder
```
6. del（Delete）：
- 作用：刪除文件。
- 用法：
 - del [文件名稱]：刪除指定的文件。
 - del /f [文件名稱]：強制刪除只讀文件。
 - del /s [文件名稱]：刪除當前目錄及其子目錄中的指定文件。
- 範例：
```shell 
del file.txt
del /f readonlyfile.txt
del /s *.tmp
```
7. copy：
- 作用：複製文件。
- 用法：
    - copy [源文件] [目標路徑]：將文件複製到指定目錄。
- 範例：
```shell 
copy source.txt C:\backup\
```
8. move：
- 作用：移動文件或文件夾。
- 用法：
    - move [源文件或文件夾] [目標路徑]：將文件或文件夾移動到指定目錄。
- 範例：
```shell
move oldFolder C:\newLocation\
```
9. rename 或 ren：
- 作用：重命名文件或文件夾。
- 用法：
    - rename [舊名稱] [新名稱]：重命名文件或文件夾。
- 範例：
```shell
rename oldname.txt newname.txt
ren oldfolder newfolder
```
10. echo：
- 作用：在命令行輸出文本，或用於顯示環境變量的值。
- 用法：
    - echo [文本]：顯示指定文本。
    - echo %環境變量名%：顯示指定環境變量的值。
- 範例：
```shell
echo Hello, World!
echo %JAVA_HOME%
```
11. path：
- 作用：顯示或設置系統的環境變量PATH。
- 用法：
    - path：顯示當前的PATH環境變量。
    - path [新路徑]：設置新的PATH值（注意：這將覆蓋現有的PATH值）。
- 範例：
```shell
path
path C:\Program Files\Java\jdk1.8.0_221\bin
```
12. javac：
- 作用：編譯Java源文件。
- 用法：
    - javac [文件名.java]：編譯Java源文件，生成相應的字節碼文件（.class）。
- 範例：
```shell
javac HelloWorld.java
```
13. java：
- 作用：運行Java字節碼文件。
- 用法：
    - java [主類名]：運行編譯後的Java程序。
- 範例：
```shell
java HelloWorld
```
14. exit：
- 作用：退出命令提示符窗口。
- 用法：
    - exit：關閉命令提示符窗口。
- 範例：
```shell
exit
```
###### 總結
掌握這些常用的DOS命令行指令對於Java開發者來說非常重要。這些指令不僅有助於管理文件和目錄，還能幫助在命令行中編譯和運行Java程序。在日常開發工作中，靈活運用這些命令可以提高工作效率並更好地理解操作系統與Java開發環境的交互方式。