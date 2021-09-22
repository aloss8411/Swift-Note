[[unwind segue]]

Dynamic Prototypes ->不固定行數的表格內容

優先採用：UITableViewController
• 方便,iOS 預先將 table view controller 設為 table view 的 data source & delegate。
• 表單輸入頁面常搭配UITableViewController,因為鍵盤出現時會自動 scroll,不會遮住輸入框。

使用UITableView表格顯示時,需要知道
•有幾個 cell
•每個 cell 的內容是什麼並找 data source,delegate(資料來源)幫忙

![[Pasted image 20210817114135.png]]
![[Pasted image 20210817114229.png]]

•表格被點選時請 delegate 幫忙,由 delegate 決定要做什麼。

•表格顯示資料時,請 data source 幫忙,由 data source 決定
cell 的數量和內容。


表格資料的來源

• 資料存在 array
• 在程式的 array 裡直接指定
array 裡的東⻄會對應 cell,第一個東⻄對應第一個
cell,第二個東⻄對應第二個 cell
• array 內容如何取得
• 從程式設定固定的內容
• 從網路抓取
• 讀取檔案


一定要設定Identifier

可從參數 indexPath 得到 section & row
![[Pasted image 20210817135654.png]]

重複使用cell
let cell = tableView.dequeueReusableCell(withIdentifier:"l0verCell", for: indexPath)


從 iOS 15 開始,使用內建 cell 樣式建議搭
配 iOS 14 推出的UIListContentConfiguration:

override func tableView(_ tableView: UITableView, cellForRowAt indexPath:
IndexPath) -> UITableViewCell {
let cell = tableView.dequeueReusableCell(withIdentifier:
"loverCell", for: indexPath)
let lover = lovers[indexPath.row]
var content = cell.defaultContentConfiguration()
content.image = UIImage(named: lover.imageName)
content.imageProperties.maximumSize = CGSize(width: 200, height:
200)
content.text = lover.name
content.secondaryText = lover.intro
cell.contentConfiguration = content
return cell

}

@IBSegueAction 傳資料搭配if let

@IBSegueAction func showDetail(_ coder: NSCoder) -> LoverDetailViewController? {
if let row = tableView.indexPathForSelectedRow?.row {
	return LoverDetailViewController(coder: coder, lover: lovers[row])

} else {
	return nil
	}

}

indexPathForSelectedRow
table view 的 property,型別為 IndexPath?,代表目前被選取的 cell 的 index path


Cell的高度問題
解法 1: 讓 cell 固定高度 ( 適合每個 cell 一樣高度)

• 解法 2: auto layout 自動計算高度(適合每個 cell
不同高度,比方聊天訊息,待會說明)
• 解法 3: 定義 UITableViewDelegate 的
tableView(_:heightForRowAt:)
• 解法 4: UIListContentConfiguration 會自動依
據內容調整高度


客製化不同的Cell 
let cell = tableView.dequeueReusableCell(withIdentifier: "boyCell", for: indexPath) as!
BoyTableViewCell
let cell = tableView.dequeueReusableCell(withIdentifier: "girlCell", for: indexPath) as!
GirlTableViewCell

透過 data source & delegate去客製功能

• 定義型別 A 遵從 protocol
• 在型別 A 裡定義 protocol 的 function
• 指定 data source or delegate 是型別 A 生成的東⻄
UITableViewController 只要做第二個步驟,定義 protocol 的 function

用 auto layout 計算 cell 高度
解法 1: 讓 cell 固定高度
解法 2: auto layout 自動計算 cell 高度
解法 3: 定義 UITableViewDelegate 的tableView(_:heightForRowAt:)
解法 4: UIListContentConfiguration 會自動依據內容調整高度

判斷點選的是哪一個Cell
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用轉換座標的-convert-function-判斷點選的-cell-1eee56a57d3b


編輯表格->canMoveRowAt
https://ithelp.ithome.com.tw/articles/10209487


表格新增
表格刪除
表格編輯
unwind segue
	![[Pasted image 20210902084508.png]]
	![[Pasted image 20210902084535.png]]
prepare

將資料回傳的方式
![[Pasted image 20210902082019.png]]


Long Press do move cell
https://www.raywenderlich.com/2474-cookbook-moving-table-view-cells-with-a-long-press-gesture