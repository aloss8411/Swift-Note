[get,set]
[didget,didset]

意味指計算屬性 -> 偽裝成變數的func
讀取時都會被重新計算過一次

一般儲存資料的屬性我們稱為stored property，擅長記憶

![[Get,Set.jpg]]

上圖可知當程式碼讀取時，會執行get{}中的程式
當利用新的變數值回傳時，則會執行set{}中的程式
但通常兩者不會一起使用



在property中宣告willSet didSet -> 偵測屬性變化
willSet將在屬性即將設定時被呼叫(在屬性變化前先做點什麼)
didSet將在屬性已設定時被呼叫(在屬性變化後更新點什麼)


var formattedDuration: String
{ 
let minutes = duration / 60 
let seconds = duration % 60 
return "\(minutes)分\(seconds)秒"
}



規則：

Computed property must have an explicit type -> 需要指定型別 (var後面)

不需要初始值

每次讀取都會重新計算，回傳計算的結果，怎麼算也算不膩。