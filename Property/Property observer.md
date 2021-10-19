應用：

class LoverTableViewController: UITableViewController {

var lovers = [Lover]() {
	didSet {
		Lover.saveLovers(lovers)
			}
		}
}


[[Get,Set.jpg]]