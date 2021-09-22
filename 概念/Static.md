 Static : static無法被覆寫
>type property：變成專屬於此物件的 property，其他人不能用

可直接從型別存取，不須先生成資料
什麼時候使用static？-> 唯一的，屬於型別的東西，不會因為個別生成資料而不同
· 更方便、常用的讀取、建立資料，任何地方、檔案都可存取，不像變數有範圍限制

在 Swift 中，我們偶爾會用到 `static` 這個 keyword 來讓某個 method 或 property 被宣告成所謂的 _type method_ 或 _type property_。這個做法常常用在用來建構物件的 _factory method_ 上面，比如說：
範例：

`class Baby {
	var name = ""
	var star = ""
	static var maxAge = 100

	static func createWhiteAquariusBaby() -> Baby {
		let cuteBaby = Baby()
		cuteBaby.name = "peter"
		cuteBaby.star = "水瓶"
		return cuteBaby
	}
}

let maxAge = Baby.maxAge
let cuteBaby = Baby.createWhiteAquariusBaby()



class Dog {  
  
let sex: Sex  
  
static func makeMaleDog() -> Dog {  
		return Dog(sex: .male)  
}  
  
}  
 
// 使用 static method  
let lucky = Dog.makeMaleDog()
`


