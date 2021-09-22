IBAction中的sender可用來判斷是哪一個元件被使用

適合搭配Outlet Collection做使用

Example:

@IBAction func tap(_ sender: XX){
	sender此時被視為使用的元件
}

Example
`
@IBOutlet var buttons:[UIButton]!
`

Outlet Collection是有順序的，可查詢看看。