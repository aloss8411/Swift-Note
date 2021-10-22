Plist文件-Property List，是一種存儲工具，用來儲存序列化後的物件

通常會使用儲存使用者設定


優缺點：優點是可視化很直觀的看到文件內容而且便於直接操作文件，缺點是因為其一般作用於固態的數據形式保存而經常變動的數據不好操作了
適用：適用於固態的數據存儲
存儲類型：NSArray、NSDictionary、NSData、Boolean、NSDate、NSNumber、NSString


建立好Plist檔案後，PropertyListDecoder進行解析，方法近似於JSONDecoder

->範例Code如下
![[Pasted image 20211021095740.png]]

ForResource：你要使用的Property
withExtension：檔案格式，選擇plist

儲存方式：
Plist檔案由於是以binary形式來儲存, 所以檔案較小, 如果考慮到檔案的大小,  需要最優化檔案大小時， 就用Plist。

什麼是Binary ->

中文：二進位檔案

英語：Binary file

-   廣義的二進位檔案即為檔案，由檔案在外部儲存裝置的存放方式為二進位而得名。
-   狹義的二進位檔案即指除文字檔案以外的檔案。

也就是說所有的檔案都是Binary。但如果我們用狹義的定位，是除了「ASCII」之外的所有檔案