URLSeisson -> 負責協調網路資料以及APP


利用背景下載圖片：
利用 background thread 在背景抓資料。因此 main thread還可以做事,使用者還可以操作 UI


URLSession.shared.dataTask(with: url) { data, response , error in
	if let data = data {
	let image = UIImage(data: data)
	print("get image", image)
	}
}.resume()


![[Pasted image 20210831200212.png]]


使用WKwebView -> 進行網頁載入
      

import WebKit
class ViewController: UIViewController ,UIWebViewDelegate{

 @IBOutlet weak var web:WKWebView!

 override func viewDidLoad() {

	 super.viewDidLoad()

	 let url = "https://www.pinterest.com"

 if let urlstr = URL(string: url){

 	let request = URLRequest(url: urlstr)

	 web.load(request)

 }

 }      

>URLrequest抓資料可調整部分細節

let request = URLRequest(url: url,cachePolicy: .returnCacheDataElseLoad, timeoutInterval: 30)

URLSession.shared.dataTask(with: request) { data, response,
error in
	if let data = data {
	}
}

資料暫存機制
https://developer.apple.com/documentation/foundation/nsurlrequest/cachepolicy

· reloadIgnoringCacheData(重新抓取)
· returnCacheDataElseLoad (讀取暫存的資料,若無暫存則重抓)

API key 通常透過以下 3 種方法帶在 request 裡:

-   帶在網址的 query 字串
-   帶在 HTTP header。
-   搭配雜湊演算法讓 API key 更安全

