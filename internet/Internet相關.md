import UIKit
import Foundation

let url = "https://www.ptt.cc/bbs/Web_Design/M.1605819375.A.483.html"

if let url = URL(string: url){

let data = try? Data(contentsOf: url)

}

>看到 throws 表示生成 Data 時可能會失敗,失敗的話會丟出錯誤

想要從網路上抓取圖片放於UIImage -> 不可直接生成UIImage，但可以抓Data後傳遞

網路上的保密->一定要記得添加https



API-Key
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/以-api-key-串接心有設防的api-a499dee188e8

測試URLRequest取得的JSON資料
https://medium.com/彼得潘的-swift-ios-app-開發教室/從-playground-預覽-urlrequest-取得的-json-資料-http-get-5bf310b163d4