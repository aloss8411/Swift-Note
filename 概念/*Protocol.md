[[enum]]
[[Class vs Struct]]
[[Delegate]]


使用方式：只宣告不定義
class,struct & enum 都可以遵從 protocol
遵從(adopt) protocol 代表會有 protocol 的能力
答應定義 protocol 裡宣告的 function
Example:

protocol dol{
		func handsomeguy()
		func yoo()
	}
	
class baby :Idol{
	func handsomeguy(){
		}
	func yoo(){
		}
}

遵從protocol類似繼承，但必須遵從protocol的內容
protocol可以當成型別來使用

Equatable 的 struct & enum 定義 == function
有時我們無法直接使用== 來進行比較
如以下例子：
struct Man { 
	var name: String 
	var height: Double
	}
	let man1 = Man(name: "彼得潘", height: 180.5)
	let man2 = Man(name: "金城武", height: 180.5)
if man1 == man2 {} ->無法比較

但只要讓型別遵守protocok Equatable，定義static fuction ==
如以下例子
struct Man: Equatable {
	var name: String 
	var height: Double 
	static func == (lhs: Man, rhs: Man) -> Bool{
		return lhs.height == rhs.height
		}
	}
	即可比較兩者定義
	
	
自定義function ==

struct Employee: Comparable {
var firstName: String
var lastName: String

static func == (lhs: Self, rhs: Self) -> Bool {
	lhs.lastName == rhs.lastName
}

static func < (lhs: Employee, rhs: Employee) -> Bool {
	lhs.lastName < rhs.lastName
	}
}
	
	
	
	
	
當有非常多的property需要比較時，Swift預設只要遵守Equatable即可比對每個function的 == ，唯有全部都相等時回傳ture

注意：兩者的property必須相等，若無法相等則不會自動定義

當為enum時， 若有associated value 時，比對也很麻煩，因為要一一比對每個 value

enum Status {
case 
	onTime 
case 
	delayed(minute: Int, second: Int)
static func == (lhs: Status, rhs: Status) -> Bool { 
	switch (lhs, rhs){
		case (.onTime, .onTime): return true
		case (.delayed(let lhsMinute, let lhsSecond), .delayed(let rhsMinute, let rhsSecond)):
		return lhsMinute == rhsMinute && lhsSecond == rhsSecond 
		default: return false
				} 
			}
		}