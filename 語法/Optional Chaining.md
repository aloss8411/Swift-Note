什麼是Optional Chaining?
利用 optional binding，我們可以防止因為讀取 nil 造成的閃退問題。但有時它卻會產生剪不斷，理還亂，層層錯綜複雜的 if let 程式碼，例如以下例子
`class Rabbit { 
var name = "白彼得" 
func run() { 
	print("跑跑跑")
}}
class Baby {
	var cuteRabbit: Rabbit? = Rabbit()
	}
var cuteBaby: Baby? = Baby()
	if let cuteBaby = cuteBaby {
		if let cuteRabbit = cuteBaby.cuteRabbit {
			let message = "寶寶的兔子是\(cuteRabbit.name)" print(message) 
			}
		}
`

有時候我們會需要進行多層的Optional binding，會導致程式碼太多層雜亂，所以可以利用逗號串接多個Optional binding，但這樣有時候有多個變數依然會促使程式碼雜亂。
所以出現了另外一個作法讓，我們可以利用?.存取，若變數出現nil值則不再繼續讀取下去，直接回傳nil而不繼續unwrap
此方式我們稱為Optional Chaining
`
var cuteBaby: Baby? = Baby()
cuteBaby?.cuteRabbit
cuteBaby = nil
cuteBaby?.cuteRabbit
`
