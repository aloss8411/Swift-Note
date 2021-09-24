![[Pasted image 20210922103307.png]]


具體方式：如上圖
在特定頁面建立Protocol，並設計Protocol所需要遵循的func，利用Extension將func內容定義清楚。
此func -> 定義該做什麼，此處為傳遞資料使用，亦可進行其他的操作

//此處為將代理權轉給另一個ViewController，讓下一個ViewController能夠操作（Ex:傳遞資料)
[@IBSegueAction]func showSelectAnimal(_ coder: NSCoder) -> SelectAnimalViewController? {  
let selectAnimalViewController = SelectAnimalViewController(coder: coder)  
**selectAnimalViewController?.delegate = self  
**return selectAnimalViewController  
}






參考觀念：
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-delegate-讓不同元件溝通-以資料回傳到前一頁-controller-為例-ba215f3d2596


https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/定義-controller-的-init-設定-delegate-e50fd6bc5509


https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/自訂-delegate-範例-develop-in-swift-data-collections-重點整理-ca17c451643e

試著練習範例：
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/定義-controller-的-init-設定-delegate-e50fd6bc5509



Unwind Sugue傳遞資料以及Delegate傳遞資料