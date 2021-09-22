![[Pasted image 20210922103307.png]]

建立Protocol ->讓使用上有著更多地彈性

protocol SelectAnimalViewControllerDelegate {}  
class SelectAnimalViewController: UIViewController {  
      
var delegate: SelectAnimalViewControllerDelegate?








參考觀念：
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-delegate-讓不同元件溝通-以資料回傳到前一頁-controller-為例-ba215f3d2596


https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/定義-controller-的-init-設定-delegate-e50fd6bc5509


https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/自訂-delegate-範例-develop-in-swift-data-collections-重點整理-ca17c451643e

試著練習範例：
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/定義-controller-的-init-設定-delegate-e50fd6bc5509



Unwind Sugue傳遞資料以及Delegate傳遞資料