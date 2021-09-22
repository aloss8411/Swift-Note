初始化內容

須遵守的規則

-   原則一: 屬性的初始，必須在當初宣告屬性的類別裡進行。
-   原則二: 子類別得先完成自己屬性的初始後，才能進行父類別屬性的初始。

生成東西時將執行init{}中的內容，會在其中設定屬性的內容
· 無設定時，Swift將自動生成（無參數的initializer)
Example : 
宣告值
`
class babyrage{
	var age:Int
	var name:String b ,m
	
	init(){
		age = 1
		name = "God"
	}
}`
var babySetting = babyrage() 
//babySetting  = God , 1

· 若class的property未指定內容或未設為Optional，則要定義init設定內容
Example:

`class babyrage{
	var age:Int = 1
	var name:String  //未設定內容
}`
//系統顯示class "babyrage" has no initializers


接受特定參數的initializer 
`class babyrage{
	var age:Int 
	var name:String
	init(newAge:Int , newName:String){
		age = newAge
		name = newName
	}
	var cutebaby = Baby(newAge:1 ,newName:"God")
}`
//亦可以在init給予屬性數值，ex:newName:String = "God"

利用self區分property以及參數 ->有self的是property
`class Baby {
	var age: Int
	var name: String

init(age: Int, name: String) {
	self.age = age
	self.name = name
}
}
var cuteBaby = Baby(age: 1, name: "peter")
`

init可以有很多種，生成各種參數的方式

[[Static]]Type Prperty無法在init中設定內容且須設定內容或設為Optional
type property -> 無法在init中宣告

先宣告子類別本身的項目後才可呼叫父類別的initializer初始age->super.init() 

`class Person {
	let name: String
	init(name: String) {
	self.name = name
	}
}
class Student: Person {
	var favoriteSubject: String
	init(name: String, favoriteSubject: String) {
	self.favoriteSubject = favoriteSubject
	super.init(name: name)
	}
}`

以init存取其他東西
`
let redView = UIView(frame: CGRect(x: 0, y: 0, width: 100, height: 100))
redView.backgroundColor = UIColor.init(red: 1, green: 0, blue: 0, alpha: 1)
redView.backgroundColor = .init(red: 1, green: 0, blue: 0, alpha: 1)
`


當controller 完全從程式生成，不透過 storyboard，其實可以自訂 init 設定 property，不過此時我們還是要定義 init(coder:)，因為它是 required

`class ViewController: UIViewController {
var movies: [String]
init(movies: [String]) { 
	self.movies = movies 
	super.init(nibName: nil, bundle: nil) 
	}
required init?(coder aDecoder: NSCoder) { 
	self.movies = [] super.init(coder: aDecoder) 
}`


Debug:
      

'super.init' isn't called on all paths before returning from initializer ->解法
加入super.init(nibName: nil, bundle: nil)
但WHY?


super.init
->class Person {
	let name: String
	init(name: String) {
		self.name = name
	}
}
class Student: Person {
	var favoriteSubject: String
	init(name: String, favoriteSubject: String) {
		self.favoriteSubject = favoriteSubject
		super.init(name: name)
	}
}
• 呼叫父類別的 init,初始父類別裡宣告的 property 的內容
• 要先初始自己的 property 再呼叫 super.init
- 原因是：要從父類別 Person 初始 name 的內容,因為 name 在父類別宣告