# 最基礎的版本
建立struct

Ex:  

	import Foundation

	struct instrgram:Codable{

		 let id:String

		 let name:String

 		 let imageUrl:String

	}
	
建立出需要獲取的資料部分，獲取後資料會先儲存於data中(URLSession.shared.dataTask)，之後再將資料儲存於建立之變數

接著利用KeyDecodingStrategy 型別的 keyDecodingStrategy，透過它可控制 JSON 欄位名稱的轉換
open var keyDecodingStrategy: JSONDecoder.KeyDecodingStrategy

將資料data傳入自訂型別當中
let searchResponse = try decoder.decode(struct物件, from: data)


# 實際部分
由於JSON檔會有許多不同種類的型態，像是物件包陣列、陣列包屬性，因此會因應不同的資料型態做適當的處理

當有許多物件時，會以let來分別儲存資料，但若這個屬性本身是屬於陣列，則會以[xxx]作為儲存的陣列，而[xxx]會建立起新的一個struct用以儲存資料。

而後針對不同型別名稱來對於每個JSON檔物件進行改名，參照Enum,CodingKeys之運用。 



https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/ios-解碼-編碼-json-的文章整理-d3f6aa7abf95

若需要自訂特定的資料型態，使用enum CodingKeys ->描述JSON如何對應Property，定義 enum CodingKeys 的基本規則如下:

-   名字叫 CodingKeys。(ps: 若要取其它的名字，須另外定義解析 JSON 的 init(from:) )
-   遵從 protocol CodingKey。
-   將每個 property 寫成 case，case 名稱等於 property。若 property 名稱和 JSON key 的名字不一樣，再將 key 的字串設為 case 的 raw value。
-   raw value 型別為 String。(ps: 為了設定對應的 JSON key，我們必須使用字串型別的 raw value，不然是可以不使用 raw value )


[[enum]][[Initializer]][[codingkey]]