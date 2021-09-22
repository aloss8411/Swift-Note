[[Class vs Struct]]
[[*Tuple]]
[[enum]]
[[Optional Binding]]
[[資料傳遞]]
class、function、closuer屬於Reference type
struct、enum、tupled屬於Value type

在設定常、變數儲存內容時，這兩種type將產生很大的差別
· Value Type將原本的資料複製產生新的資料
· Reference Type共享同一份資料

而Swift 的基本型別，諸如 Int，String，Array，皆由 struct 定義。

當碰上Optional Binding
`struct Baby { 
	var name = "Peter"
}
var cuteBaby: Baby? = Baby()
if var anotherBaby = cuteBaby {
	anotherBaby.name = "Andy"
}
cuteBaby?.name`
會產生複製效果，但兩者值不會相同，cutebaby = Peter ,AnotherBaby = Andy

也許有人會想到，value type 每次都要複製，效能應該會比較不好。不過其實不用太擔心，Swift 很聰明，針對某些 value type 它應用 copy on write 的技巧讓效能更好。

像 String 型別即運用了 copy on write 的技巧，因此它不會馬上複製，它只在內容修改時才進行複製


當以 let 宣告的常數指到物件時，物件的屬性依然可以修改。因此以下例子的 superIdol 可以改名為小王子，年紀也可以從 18 增長為 20。
`class Idol { 
var name: String 
var age = 18 
init(name: String){
	self.name = name }}
let superIdol = Idol(name: "彼得潘")
superIdol.age = 20
superIdol.name = "小王子"
`
不能變的是此常數儲存的物件記憶體位址，它必須永遠指著同一個物件，因此我們不能用 `superIdol = Idol(name: "虎克")` 將偶像改成虎克。

如果是 value type，限制將會更多。value type 的常數本身就是資料，因此資料的屬性也不能修改。

關於Array

Swift 的 array & dictionary 皆由 struct 定義，屬於 value type。當我們設定 array A 等於 array B 時，將複製產生一個新的 array。然而 array 的成員是 value type 還是 reference type，將讓程式的結果有很大的差別。

我們開發 iOS App 時，MVC 裡的 model 可用 class 定義，也可用 struct 定義。關於哪個比較好，一直是個眾人爭論的話題。基本上若無特別的考量，選擇 struct 較好，因為程式會更安全，比較不易有 bug。

當牽扯到頁面間的資料傳遞時，我們要特別注意 value type 和 reference type 的影響