可實現自動跳轉頁面，block後區域為所要運轉的程式碼內容
 var timer = Timer()

 let vc = storyboard?.instantiateViewController(withIdentifier: "Login")

 timer = Timer.scheduledTimer(withTimeInterval: 5, repeats: "false", block: {

 (timer) in

 self.present(vc!, animated: "true", completion: "nil")

 }
 
 

使用語法：
Timer()
scheduledTimer
present