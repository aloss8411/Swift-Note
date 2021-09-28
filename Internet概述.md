我們使用URLSession.shard.dataTask進行資料的下載及抓取（會先用postman進行測試），接著使用JSONDecoder將資料導入我們設定好的自訂型別當中。

Notice：可以一次性的抓取所有的資料或者是因應不同需求分別抓取，所以在網址處會因應不同的需求來抓取相對的目標（？

當遇到整個JSON檔中是有陣列時，可宣告兩個不同的struct來建立自訂型別，也可以利用struct包struct來獲取整份資料（包含Array的struct）

Ex:![[Pasted image 20210927145530.png]]

若要依照不同的API URL抓取JSON則利用baseurl來進行開發，待研究

https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/使用-baseurl-urlcomponents-urlqueryitem-產生-url-1e4539a33a89



