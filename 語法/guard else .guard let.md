guard 跟 if 一樣，後面都是接結果為 true 或 false 的條件

For Example:

guard age>19 else{
	程式碼
}
->若條件沒達成則執行程式碼

-   guard 後專門描述我們希望成立的條件。當條件成立時，程式將離開 guard 搭配的 else { }，繼續往下執行我們希望條件成立時做的事。
-   當 guard 的條件不成立時，將執行 else { } 的程式。
-   else { } 的程式執行後，必須離開 guard 所在區塊，如此才不會繼續往下執行條件成立時要做的事。就像剛剛的例子，我們利用 return 離開 function motherSay。

guard let為同理，可搭配continue