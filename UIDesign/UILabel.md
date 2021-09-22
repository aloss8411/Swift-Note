-   Dynamic Type → 讓使用者自行從設定中決定字體大小
-   Line Break
    -   Word Wrap → 以單字為單位來進行判斷是否需要換行
    -   Truncate ... → 依照結尾詞決定開頭、中間、結尾誰要進行縮排
    -   line設為0行時，預定看字決定行數
    
-   AutoShrink
    -   當字數超過元件大小時，自動進行縮小避免出現「...」
-   Miniunm&Maxnim會依照縮放比例顯示全部的文字

程式碼Example
`let loveLabel = UILabel(frame: CGRect(x: 0, y: 0, width: 300, height: 40))
loveLabel.backgroundColor = UIColor(red: 1, green: 1, blue: 0, alpha: 1)
loveLabel.text = "在天願作比翼鳥"
loveLabel.textAlignment = .center
loveLabel.borderStyle = .roundedRect`
