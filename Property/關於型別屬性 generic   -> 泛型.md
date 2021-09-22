[Generic]     
屬於通吃型，意味著可接受不同類型的型別
![[Pasted image 20210901113416.png]]

>文章解釋
https://www.appcoda.com.tw/swift-generics/
https://hugolu.gitbooks.io/learn-swift/content/Advanced/Generic.html


通用型別<Generic type>
	-   函式名稱後使用`<T>`宣告Generic Type用法。
	-   原先函式中有關型別的關鍵字通通替換成`T`。

func swapTwoValues<T>(a: T, b: T) -> (T, T) {
    return (b, a)
}

swapTwoValues(1, 2)             //return: (.0 2, .1 1)
swapTwoValues(3.14, 2.71)       //return: (.0 2.71, .1 3.14)
swapTwoValues("foo", "bar")     //return: (.0 "bar", .1 "foo")

為型別加上限制條件
	
Where 後可加入各種條件（Protocol協議）
	![[Pasted image 20210901155454.png]]

![[Pasted image 20210901155458.png]]
	