分為Strong Reference cycle(retain cycle) and Weak Reference cycle 

當物件因reference cycle而不會消滅時，需在前面加上weak解決該問題
加上weak則代表：該物件不會被加入Reference中，物件死亡後會被設為nil



來自記憶體爆炸前的警告:

UIViewController

	func didReceiveMemoryWarning()

UIApplicationDelegate

	func applicationDidReceiveMemoryWarning(_ application:UIApplication)

減少記憶體用量,比方移除用不到的 view

-------------------------------------------------

自動追蹤reference物件的數字。當數字為0時,物件即死亡

• 只作用在物件,不會作用在 struct & enum(struct & enum 是 value type,是複製的概念)

-------------------------------------------------
類別解構函式  ->  deinit -> 反初始化
	負責處理在類別消除前執行一些動作，我們可以利用這個函式觀察物件的生命週期
	
	
-------------------------------------------------
當物件被加到 array 或 dictionary 時,也會增加 reference.


待研究：unowned 

[[unowned]]



