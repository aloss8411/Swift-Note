[[資料傳遞 Segue]]

其中包含alert(置中), actionSheet(從下出現）兩種樣式以及添加文字的textfield

//先宣告你要的東西
let  controllers = UIAlertController(title: "這是測試標題", message: "我要告訴你的訊息", preferredStyle: .alert)
//你要執行的動作，並生成按鈕
 let  action = UIAlertAction(title: "OK", style: .default, handler: nil)
//將動作加入UIAlertcontroller
 controllers.addAction(action)
//事件出發後呈現出畫面
 present(controllers, animated: true, completion: nil)
 
 
 樣式講解
 .alert將顯示從中間彈出的視窗
 .destructive描述性寫法
 
 style負責控制樣式設計
 handler傳入closure負責點選按鈕要做的事情
 
 加入textfield
      
  `
**@IBAction** **func** tapButton(){

 **let** alert = UIAlertController(title:"測試使用", message: "Tell me Why", preferredStyle: .alert)

 alert.addTextField{(textField) **in**

 textField.placeholder = "開心ㄇ"

 }

 **let** action = UIAlertAction(title: "告訴我", style: .destructive , handler: **nil**)

 alert.addAction(action)

 present(alert, animated: **true**, completion: **nil**)

 }
 `
 
 如何加入textView
 
 研究這一串->
 `
 swift
var height:NSLayoutConstraint = NSLayoutConstraint(item:alertController.view, attribute: NSLayoutConstraint.Attribute.height, relatedBy:NSLayoutConstraint.Relation.equal, toItem: nil, attribute: NSLayoutConstraint.Attribute.notAnAttribute, multiplier: 1, constant: self.view.frame.height * 0.80)
 alertController.view.addConstraint(height);
`

--------------以上為螢幕置中選單--------------

//先宣告你要的東西
let  controllers = UIAlertController(title: "這是測試標題", message: "我要告訴你的訊息", preferredStyle: .actionSheet)
//你要執行的動作，並生成按鈕
 let  action = UIAlertAction(title: "OK", style: .default, handler: nil)
//將動作加入UIAlertcontroller
 controllers.addAction(action)
//事件出發後呈現出畫面
 present(controllers, animated: true, completion: nil)
 
 