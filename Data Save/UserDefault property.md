UserDefaults:永久存在

適用例子: App 的相關設定資料,
比方是否是第一次打開 App,上次打開 App 的時間 ,
上次停留的 App 畫面,遊戲的最高分
user’s defaults database

App 啟動後將資料載入到記憶體,方便快速讀取

>不應該被儲存大量資料  >屬於Apple本身的property list
>![[Pasted image 20210906150415.png]]


自訂資料儲存至UserDefault
· 變成Data
· 變成Dictionary


如何將自訂資料變成Data並儲存至UserDefaults
 ->遵從 protocol Codable 的型別資料可以解碼和編碼
 
 ![[Pasted image 20210906151442.png]]

Warning:
UserDefault資料過多：
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/userdefaults-存太多資料會怎樣-3dbde84ca884


圖片存檔時，該如何命名：
將圖片名稱存到 model 的欄位,比方型別 Lover 的 imageName,如此之後 Lover 存檔後(比方存在 lovers.plist),將來讀取即可取得圖片名稱,再從圖片名產生路徑生成 image

- 參考解說：https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/ios-app-如何產生獨一無二的-id-a1facb7377d3


#todo
- [x] 從56頁開始 -> 資料儲存