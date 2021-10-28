是一種網路傳遞概念，是為了更好的遵守HTTP協定（超文本傳輸協定）

狀態碼Ststus Code又會再分為下幾種：

2xx = Success（成功）  
3xx = Redirect（重定向）  
4xx = User error（客戶端錯誤）  
5xx = Server error（伺服器端錯誤）


在 HTTP 中，會有很多種 method 做為請求的方法，常用的幾個動作分別為：GET / POST / PUT / DELETE，正好會對應到資料庫基本操作 CRUD 增刪查改。

RESTful API 主要由三種元件組成：

1.  Nouns 名詞：定義資源位置的 URL，每個資源在網路上都會有唯一的位置，就如每戶人家都有唯一的地址一樣。
2.  Verbs 動詞：對資源要做的動作。
3.  Content Types 資源呈現方式：API 資源可以以多種方式表現，最常用的是 JSON，較輕，也較好處理。


# 若以 RESTful API 風格開發的話：

獲得資料GET     /data  
新增資料POST    /data  
刪除資料DELETE  /data/1

就是用一個唯一的 URL 定位資源，將動作藏在 HTTP 的 method 裡面

# RESTful 風格設計的 API，就有了以下幾種優點及限制：

1. 有唯一的URL表示資源位置，統一的 API 接口。(Uniform Interface)

2. 無狀態。(Stateless)

3.  可更高效利用快取來提高回應速度 (Cachable)

4.  分層系統架構 (Layered System)

5. 客戶端服務器分離 (Client-Server)

6. 充份利用 HTTP protocal(GET/POST/PUT/DELETE) (Manipulation of resources through representations)
7. 7. 可執行程式碼的設計，像是 JavaScript（非必要實作項目） Code-On-Demand (optional)


只要能串接統一的底層URL入口，並利用泛型解決JSON Data to Model的轉換，亦可以結合 PromiseKit 與 Alamofire，製作屬於你的非同步 API 網路應用。


上傳資料：

HTTP method  = RESTful API
HTTPbody內放入要上傳的資料
