JSON 是一種資料格式，主要以 [ ]，{ }，字串，數字 & bool(true或false) 描述資料的內容

[ ] 表示 array，比方以下 [ ] 裝著 6 首好聽的小xx 情歌
{ } 表示物件，以 : 描述物件的內容，: 的左邊是 key，右邊是 value

JSON 厲害的地方在於它可以包很多層，array 裡的資料可以是物件，物件的某個 key 的內容可以是 array


https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/使用-postman-研究-api-產生-swift-程式-12e9417c7352


將 JSON 變字串顯示

if let urlStr = "https://itunes.apple.com/search?term=戴佩妮&media=music".addingPercentEncoding(withAllowedCharacters:.urlQueryAllowed),let url = URL(string: urlStr) {

URLSession.shared.dataTask(with: url) { data, response, error in

if let data = data,
let content = String(data: data, encoding: .utf8){
print(content)
}

}.resume()
}

https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用中斷點將-json-data-變成字串-808a5a152129


解析JSON資料
![[Pasted image 20210830085138.png]]

解釋URLSession
https://apppeterpan.medium.com/為什麼-urlsessiontask-要呼叫-resume-才會啟動-27e0aaba57ef


https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-swift-4-的-jsondecoder-和-codable-解析-json-和生成自訂型別資料-ee793622629e


客製化JSON資料
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-enum-codingkeys-客製-json-對應的-property-1b27f29c0c32


轉換JSON資料格式
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-keydecodingstrategy-的-convertfromsnakecase-自動轉換-json-欄位名稱-swift-4-1-a0164dde3565


Date型別
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/jsondecoder-解析時間的-datedecodingstrategy-a4095481f193

https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/ios-解碼-編碼-json-的文章整理-d3f6aa7abf95