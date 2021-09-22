[[Class vs Struct]]
[[UILabel]]
[[UITextField,UITextView]]
[[UIView]]
[[*Protocol]]
[[assoicated value]]

enum適合拿來當作清單

發明型別的三大方法class struct enum

enum基礎用法，裡面只能包含String ,Int等基礎型別

`enum Pet:String{
	case dog = "小狗" , cat = "小貓" , rabbit = "兔子"
}
var myPet :Pet = .rabbit
print(myPet.rawValue) -> 兔子
`

NSTextAlignment -> 屬於Enum
用以控制文字置左、中、右 ->適用UILabel,UITextfield,UITextView

讓enum變成array的Caselterable&Allcases ->屬於protocol

mutating 改變裡面的內容

enum內只能宣告Computed property


enum特殊語法：associated value語法，會讓enum的case具有儲存相關連資料的功能


enum&func的聯合應用
![[Pasted image 20210824104500.png]]


Associated Value
![[Pasted image 20210824112521.png]]
![[Pasted image 20210824112606.png]]

https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/enum-儲存相關聯資料的-associated-value-26ab3e061a16

https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/synthesized-comparable-conformance-for-enum-types-swift-5-3-bd587857b6d6

>值得再研究


Assoicated Value語法->讓cases能夠儲存相關連資料	
![[Pasted image 20210903104002.png]]

>Example
enum Status {  
	case onTime  
	case delayed(minute: Int, second: Int)  
}
![[Pasted image 20210903104156.png]]
![[Pasted image 20210903104322.png]]
