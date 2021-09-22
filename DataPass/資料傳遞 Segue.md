[[Property]]
[[Initializer]]
[[IBSegueAction]]
[[prepare]]
[[unwind segue]]
如何將資料傳遞到不同頁面?
· property
· 透過segue | unwind segue
· IBSegueAction -> property
· Notification
· delegate
· closure
· KVO
· global variable



1.IBSegueAction：透過IBSegueAction定義在segue起點的controller，可在func中建立下個頁面的controller及傳資料到此頁面

@IBSegueAction在透過sugue轉換頁面時觸發

coder:包含在storyboard上的東西

 
 重點是先設定第二頁的變數（選擇所需的資料）,之後再利用IBSegueAction傳遞資料過來	
 可從Segue 的 Attributes inspector中的Selector確認是否確實有傳遞資料過去
 
 第二頁設定
 設定相同變數，以用來接受上頁傳送之值，若是多筆資料的話，使用property進行多變數儲存(自訂型別Struct)，sugue太多時，利用參數sender  /  segue id進行區分
 
 更好的寫法：使用init，由參數設定property
 
 參考文獻：
 https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-ibsegueaction-傳資料到下個頁面的-controller-ios-13-新功能-50813ba3822
 
 
 shouldPerformSegue -> 語法
 ![[Pasted image 20210902090424.png]]
 ![[Pasted image 20210902090603.png]]
 ![[Pasted image 20210902090704.png]]
 
 >Example
第一頁
   
struct name{
	 let name:String
}
      
@IBSegueAction func dataPass(_ coder: NSCoder) -> webViewController? {

 let action = webViewController(coder: coder, word: name(name:textField.text!))

 return action

 }


第二頁
 let word:name?

 init? (coder:NSCoder,word:name){

 selfword = word

super.init(coder:coder)

 }
 required init?(coder: NSCoder) {
 fatalError("init(coder:) has not been implemented")

 }
 
 