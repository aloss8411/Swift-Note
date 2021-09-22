[[shorthand Arguement Name]][[Typealias]]

>使用時機
· 通常是在執行完某個 func之 後，馬上要處理某件事情時使用，例如從網路下載資料完，要馬上處理與顯示畫面時
· 不能修改別人寫的 function 程式碼但可傳入自己寫 function 當參數,即可執行自己寫的程式碼,做想做的事情。

Example 1:
![[Pasted image 20210828120813.png]]

func buyBook() -> String {
 	return "學 Swift 的都是愛買書的文藝青年"
 }
 var buyBook2 = buyBook //表達這個型別的模樣  ->   () -> String
 var buyBook3 = buyBook() //執行這個方法 -> 學 Swift 的都是愛買書的文藝青年
 
 ![[Pasted image 20210825110248.png]]
 
 
 
func中包含著func -> 可以客製化修改程式

>Example1:
 
func eatAndExercise(sport: (Int) -> String) -> String {
	return sport(8)
}

func playTableTennis(hour: Int) -> String {
	return "打桌球\(hour)小時"
}

eatAndExercise(sport: playTableTennis)

>Example2

func download(urlString: String, handler: (Data) -> Void) {
	if let url = URL(string: urlString),
		let data = try? Data(contentsOf: url) {
			handler(data)
}
}
func displayImage(data: Data) {

}
func saveImage(data: Data) {

}
download(url: "http://bit.ly/2puz11N", handler: displayImage)
download(url: "http://bit.ly/2puz11N", handler: saveImage)


> 回傳 function 的 function

func happy() -> String {
return "忘記了姓名的請跟我來,現在讓我們向快樂崇拜,放下了包袱的請跟我來 傳
開去建立個快樂的時代"
}
func sad() -> String {
return "每天這個時候,心都特別寂寞,在窗邊吹風淚會流"
}
func feeling(mood: Int) -> () -> String {
if mood > 0 {
return happy
}
else {
return sad
}
}
var todayFeeling = feeling(mood: 3)
var message = todayFeeling()

>shorthand Arguement Name 簡化說明
Closure參數的名稱變成預設代號，第一個參數為 $0，第二個參數為 $1，依此類推。因為透過$存取參數，所以原先宣告參數也沒有存在的必要，因此這樣的寫法就也可以一併省略 in	


參考資料：
https://medium.com/彼得潘的-swift-ios-app-開發教室/簡易說明swift-4-closures-77351c3bf775


closure 應用: forEach

let lovers = ["Penny", "Joi", "Paggy"]
lovers.forEach { name in
	print(name)
}
lovers.forEach { print($0)