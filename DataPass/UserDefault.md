[[DataPass/UserDefault]]
[[prepare]]
[[資料傳遞 Segue]]

傳遞資料的頁面：
 		UserDefaults.standard.setValue(textfield.text, forKey: "test")
接收資料的頁面：
		text.text = UserDefaults.standard.object(forKey: "test") as? String
		->不確定是否有值，使用as?進行判斷
		->可加入在viewDidLoad，不會造成無值nil而閃退之情況
		->適合傳遞較少的資料，大量資料不適合
		->適合搭配if let & guard let進行判斷