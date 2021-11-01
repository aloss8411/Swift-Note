xib 可設計 App 裡常出現的 UI 元件,方便重覆利用,比方 loading view
*不可以拉Segue

建立起Xib檔案後，在所需ViewController中加入
> Bundle.main.loadNibNamed( ,owner:,option:)

->[array] >意思為在該Xib檔案中將物件作為Array儲存

應用：建立一個Class，繼承自Xib檔案 
並利用上述宣告，即可於各ViewController中客製化相關內容及應用

#todo 
- [x] test



當我們從程式以 controller 名字加 ( ) 生成物件時，通常有以下兩種寫法(假設 controller 型別名稱是 DemoViewController):

1. 指定 controller 搭配的 xib 檔名。

2. ( ) 裡不帶任何東西。

DemoViewController()

如果採用第二種寫法，或是在第一種寫法的 nibName 傳入 nil，其實還是有可能跟 xib 有關。如果你沒有覆寫 controller 型別的 loadView，此時它還是會先試著找尋是否有搭配的 xib，找法如下:

(1) 如果 controller 型別名以 Controller 結尾，它將尋找名字為 controller 型別名去掉 Controller 的 xib。比方 DemoViewController 將找尋 DemoView.xib。

(2) 如果 (1) 找不到，它將尋找同名的 xib。比方 LoveSongController 將找尋 LoveSongController.xib。

如果 (1) & (2) 都找不到，才表示此時生成的 controller 沒有搭配的 xib，畫面得完全從程式製作


建立好Xib後如何加入：
利用Bundle.main.loadNibNamed ->會將Xib檔案中的畫面變成array傳回，然後再利用View.addsubView控制
也可另外建立CocoaPods，並掛名於其中一個ViewController，則可在ViewController中控制。

