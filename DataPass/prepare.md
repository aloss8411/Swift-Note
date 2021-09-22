[[資料傳遞 Segue]]    
[[Initializer]]
利用prepare來進行資料傳遞，觸動的時間在藉由segue進入下一頁前觸發，執行完prepare後才執行下頁的viewDidLoad
特點
· 需有segue才能觸發
· 隨頁面自動傳遞過去（可能會需要initializer)	


>Example:
資料頁：
override func prepare(for segue: UIStoryboardSegue, sender: UIButton ) {
	 let  target = segue.destination as? ResultViewController
	 destionation?.變數  =  要傳遞的資料
 }
 結果頁
	var 變數（給資料頁抓取的）: 型別 -> 傳遞後，內容會自動傳遞至結果頁之內容部分
  
 

https://medium.com/彼得潘的-swift-ios-app-開發教室/簡易說明xcode中的資料傳遞-使用prepare傳遞property的方式-a5666ca36114