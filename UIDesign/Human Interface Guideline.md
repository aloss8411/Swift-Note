整體動畫是流暢且充滿一致性的，並藉由流動且順暢的畫面來使得體驗是增加的。

一個UI介面會包含以下元素

-   Bar - 告訴使用者他們在哪裡，提供導覽及按鈕來傳遞資訊
-   View - 呈現畫面給使用者

### Launch

-   盡可能提供使用者一個Launch Screen，告訴使用者這個APP是運作中、快速且會回應的
-   讓APP處於一個可隨時被開啟的狀態(life cycle)

### Onboarding

-   提供一個新手教學（記得要提供Skip選項）

### Modality

-   卡片式設計，往下拖弋以回到上一頁
-   要有退回鍵
-   幫助使用者在關閉程式以前能夠確實地保存數據

### UserData

-   必須使用AppTrackingTranspaerencey framework來請求使用者同意追縱數據
-   IOS15後請求使用者用Location Button來獲取暫時的數據位置（SWIFT中為CCLocationButton)

### ShazamKit

-   於IOS 15中出現的聲音辨識能力框架
-   開源軟體，並在Android開發商中同樣可以運用

每種機型會有其不同的介面尺寸，一般來說，Iphoene會由四項元素組成，狀態欄Status Bar、導航欄Navigation、主菜單欄Submenu、內容Content組成。

不同的規格會組成不同的尺寸列表，並且會具有所謂Safe area。

按鈕應該Safe Area當中而非同時橫越Safe/Unsafe area區域。

### Navigation Bar Size

Target size 24x24 pt

Maximum size 28x28 pt

## Tab Bars

---

### 圓形

Regular tab bars 24x24 pt

Compact tab bars 18x18 pt

---

### 方形

Regular tab bars 23x23 pt

Compact tab bars 17x17 pt

### Tool Bar

Target size 24x24 pt

Maximum size 28x28 pt