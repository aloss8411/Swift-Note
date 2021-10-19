[[DataPass/UserDefault]]
[[prepare]]
[[資料傳遞 Segue]]

App 預設就有的 property list，永久存在
概念：


適用例子: App 的相關設定資料,
比方是否是第一次打開 App,上次打開 App 的時間 ,
上次停留的 App 畫面,遊戲的最高分
user’s defaults database

App 啟動後將資料載入到記憶體,方便快速讀取


用法：
傳遞資料的頁面：
 		UserDefaults.standard.setValue(textfield.text, forKey: "test")
接收資料的頁面：
		text.text = UserDefaults.standard.object(forKey: "test") as? String
		->不確定是否有值，使用as?進行判斷
		->可加入在viewDidLoad，不會造成無值nil而閃退之情況
		->適合傳遞較少的資料，大量資料不適合
		->適合搭配if let & guard let進行判斷