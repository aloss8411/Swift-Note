許多第三方 API 的網站都在官方文件裡以 curl 指令說明 API

>Example
curl https://sheetdb.io/api/v1/58f61be4dda40

curl -X POST -H "Content-Type: application/json" https://
sheetdb.io/api/v1/58f61be4dda40 -d '{"data":[{ "name":
"Scott", "age": "25" }]}'

-X: HTTP method
-H: HTTP header
-d 或 —data: 上傳的資料

可以在 terminal 測試