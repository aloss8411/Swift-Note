MVC -> Model , View ,  Controller

MVC 設計模式將一個應用程式劃分成三組元件：模型 (Model)、視圖 (View) 和控制器 (Controller)。 MVC 模式定義了這三組元件在應用程式中扮演的角色和溝通方向。在設計一個應用程式時，最重要的一個步驟是選擇或創建屬於這三組元件之一的自定義類別。三組元件都會由抽象邊界來分隔開，並跨越邊界與其他元件溝通。

MVC 雖然在理論上不錯，但它在 iOS 和 Xcode 的背景下通常無法實現，我一次又一次看到開發人員將大部分應用程式的模型（數據）和業務邏輯程式碼放入視圖控制器，所以才被人取笑是 “Massive-View-Controller” 設計模式。但這是一個自然發展的趨勢，因為視圖控制器在應用程式生命週期中扮演著一個最重要的角色：與用戶的互動。

用來對抗[複雜性]的最佳方法就是分而治之。透過[區分權責]思維模式，編寫小而邏輯集中組織的程式碼，就是控制複雜性的重要條件，正如下文將看到的 Swift [`extension` 語法結構]

MVVM -> Model , View , ViewModel

Model-View-ViewModel (MVVM) 設計模式與 MVC 的_意圖_差不多，MVVM 比 MVC 模型多添加了一個組件，稱為 ViewModel（視圖模型），它可以是 `class` 或 `struct`，但通常會是一個 class，因此可以在程式碼中傳遞同一個物件的 reference，而 ViewModel 就位於視圖控制器和模型之間。
