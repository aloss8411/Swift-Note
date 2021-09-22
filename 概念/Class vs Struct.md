兩者間有90%相似

但class是存取位置，內容固定儲存在某一地方
而struct是實地儲存，代表每一次改值都是真正的改變了內容

而struct獨有的是
• struct 無法繼承
• struct 有 memberwise initializer
• struct是 value type, class 是 reference type

何謂memberwise initiallzer?
以程式碼舉例來說，struct將自動生成以屬性名字為參數的memberwise initializer，如下

`struct Baby {  
var name: String  
var age: Int  
}  
var cuteBaby = Baby(name: "peter", age: 18)
`
因此可在產生baby時產生每個屬性的值，相較之下class不會自動產生memberwise initializer
[[Initializer]]
struct 可以自動生成 memberwise initializer，不過我們也可以定義自己想要的 init。值得注意的，一旦自訂 init，struct 將不再好心生成 memberwise initializer ＆ default initializer，此時我們只能以自訂的 init 產生資料。


