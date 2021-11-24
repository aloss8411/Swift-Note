宣告樣式，再從想要的時間抓取出來並放入      

var date = DateFormatter()

 date.dateFormat = "MM.dd"

 date.string(from: datePicker.date)
 
 
 如何抓取自己想要的時間 > Calender.current.date(byAdding..)
 
 https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用date-byadding-value-to-wrappingcomponents-計算對的時間點-40965d47f196
 
 
       
計算N個單位後的時間
let choseDay = Calendar.current.date(byAdding: .day, value: indexPath.row, to: date,wrappingComponents: false) 
· byAdding:傳入時間調整的單位，比方傳入 .day 表示以天為單位，傳入 .month 表示以月為單位
·Value:  計算Value後的時間
·to: 開始的時間點
·wrappingcomponents : 是否只計算byAdding的時間，Ex:都是天的話則不改變月份.. 

![[Pasted image 20211123114638.png]]


