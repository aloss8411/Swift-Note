https://medium.com/@ji3g4kami/swift-的-property-大統整-be9f25dfdb5f

https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/讓屬性變懶的-swift-lazy-咒語-cfcc16840bd2


在使用 lazy 時，有以下幾點規則須特別注意:

-   let 宣告的屬性不能加上 lazy。

因為 let 會產生不能改變的常數，所以不可能滿足 lazy 後來才改變屬性內容的需求。

-   computed property 不能加上 lazy。

computed property 在讀取時才計算生成東西，早已實現 lazy 後來再建立東西的目的。

-   lazy 的屬性一定要在宣告時指定初始值。

如此它才知道當屬性第一次被存取時，如何設定屬性的內容