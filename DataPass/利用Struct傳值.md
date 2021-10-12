建立一File 內含

Struct  Name {

	var user:String
	//加入所需要使用的變數
}

在目標Controller建立起通道
For Example
let username: Name

init?(coder:NSCoder , username:Name){
	self.username = username
	super.init(coder:coder)
}

required init(coder:NSCoder){
	fatalError("init(coder:) has not been implemented")	
}


