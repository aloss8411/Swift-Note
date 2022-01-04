應用：

class LoverTableViewController: UITableViewController {

var lovers = [Lover]() {
	didSet {
		Lover.saveLovers(lovers)
			}
		}
}


「willSet」就字面意思簡單明瞭，會在屬性的值更新前先被呼叫，然後將這個值當作新的常數（constant）參數傳入，假如參數沒有名稱的話，會以「newValue」的內建參數為名稱。



[[Get,Set.jpg]]