[[UITextField,UITextView]]

•無法一套設計,同時在 iPhone,iPad,
Portrait ,Landscape 都完美呈現

•為每個 case 設定不同的條件 ?
失去 Auto Layout 的意義

•Size可解決上述情況


Aspect Ratio -> 比例，可調整自身比例或兩相關物件比例

AutoLayout有分為Safe Area(有margin)以及View的邊線 -> AutoLayout部分關於Constrait to margins的選項

localization issue ->在某個語言文字變長，可能與View撞在一起

文字底部：
First Baseline: 第一行的文字底部

Last Baseline: 最後一行的文字底部

baseline: 文字底部

文字底部不等於元件的下邊界


Reverse First and Second item
	· 用以判斷兩者間的關係（比例）
	
UIImageView的配置：正常情況為imageview的大小 = 圖片大小，但若被其他contrait影響則會失去判斷，所以照片也須加上寬高。

UITextView	須設定條件才能夠判斷出寬高


優先權(priority)的配置，每個AutoLayout都有優先權的配置，介於0 - 1000之間
conttent hugging proirity（優先緊抱內容權）& content compression resistance priorities(優先抵抗壓縮內容權)

content hugging proirity:
當我們不希望 View的大小大於其內容應有的大小時，便可為此優先權設定較大的值。簡單來說，這個優先緊抱內容權越高，系統留給他的空白就會越小

因此，優先緊抱內容權越高，View 的邊界將更緊密地擁抱其內容，從而阻止視圖超出內在內容大小。


content compression resistance priorities:
當我們不希望 View 的大小小於其內容的大小時，便可為此優先權設定較大的值。簡單來說，越高的優先權表示內容越不容易被縮減

水平優先抵抗壓縮內容權設定高於寬度約束的優先權，現在 AutoLayout 便會允許 Button 的內容大小不被寬![[AutoLayout公式.jpg]]


Device Size Class ->重要，讓各種產品皆有相對合適的
分為四種![[Device_Size_Class.jpg]]

C : Compact ->被約束的空間，分為wC,hC
R：Regular ->不受約束的空間，分為wR,hR

Use Fixed Leading and Resizing Trailing Constraints的作用是？
當元件某側可以與View or SafeArea可以有著>0 = 0 的間距，這樣會出現被裁切以及不好判斷的現象，系統會出現警示。
此時可從First Item點選Respect Language Direction,會看到出現LABEL.left LABEL.leading兩種情況，這樣就可以解除警示了



-> viewDidLayoutSubviews: 由此func來設計元件出現的時間點
 
 -> 在 viewDidLoad 時元件尚未以 Auto Layout 結合 iPhone 算出真正的位置大小，此時它的位置大小是依據 storyboard 裡設定的 iPhone 尺寸搭配 auto layout 決定的。

-> 什麼時候才能取得元件真正的位置大小呢 ?
		要等到 view controller 的 function viewDidLayoutSubviews 執行時。
		

	