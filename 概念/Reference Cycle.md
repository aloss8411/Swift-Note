[[enum]]
[[Class vs Struct]]

意指有時候會出現物件相互參考而導致未被使用卻持續存在並佔據記憶體的狀況

該如何解決這個問題 -> Memory weak 記憶體洩漏 
	將可能造成Reference Cycle的物件宣告成Optional 並加上 Weak ->
	以此告知系統此變數並不會增加ARC參考數量
	->利用weak解決Reference Cycle問題
	
`
class Person {
    var name: String
    var lover: Person?

    init(name: String) {
        self.name = name
        println("\(name) is borned")
    }

    deinit {
        println("\(name) is dead")
    }
}

var boy: Person! = Person(name: "Roméo")        //output: Roméo is borned
var girl: Person! = Person(name: "Juliette")    //output: Juliette is borned

boy.lover = girl     //return: {name "Roméo" {{name "Juliette" nil}}}
girl.lover = boy      //return: {name "Juliette" {{name "Roméo" {{…}}}}}

boy = nil
girl.lover            //return: {name "Roméo" {{name "Juliette" {{…}}}}}
girl = nil
`


當物件被加到 array 或 dictionary 時,也會增加 reference
	物件存在於array中時，意味著物件正在被需要
	
--------------------------------------------------
unowned -> 另一種解決cycle的辦法
(待研究)

--------------------------------------------------
Capture list -> 用以解決closure可能產生的記憶體問題

當我們在 closure 裡使用物件時，它將對物件產生兩個重要的影響:

-   增加物件的 reference count。
-   當 closure 的程式執行完，不會再執行時，物件的 reference count 才會減少

capture list 的表達方式很簡單，在 closure 的 { } 裡，一開頭加上 [ ]，在其中指定不關心物件的變數(常數)，並搭配 unowned 或 weak，若有多個變數(常數)，只要以逗號分隔即可。



參考資料：
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-capture-list-解決-closure-可能產生的記憶體問題-a7672fab1d1f

https://hugolu.gitbooks.io/learn-swift/content/Advanced/ARC.html#Deinit


使用`weak`與`unowned`的規則：

1.  use weak capture if the class instance or property is an optional
2.  use unowned if the class instance or property is non-optional and can never be set to nil
3.  "you must ... use the in keyword, even if you omit the parameter names, parameter types, and return type"
    
4.  如果參考的物件或屬性為 Optional，使用`weak`。
    
5.  如果參考的物件或屬性不是 Optional (不可能是`nil`)，使用`unowned`。
6.  定義 Closure 要使用`in`關鍵字，即使忽略參數名稱、參數型別、回傳型別。


參考資料
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-capture-list-解決-timer-notificationcenter-造成的記憶體問題-40aeb1319b19