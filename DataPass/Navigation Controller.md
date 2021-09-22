當 controller 是由 navigation controller 加入時,此 property 將為 navigation controller,否則將為 nil：
open var navigationController:UINavigationController? { get }

UINavigation Controller管理的Controller
guard let navigationController = navigationController else { return }
let count = navigationController.viewControllers.count
let topController = navigationController.viewControllers[count-1] //倒數第一頁
let preController = navigationController.viewControllers[count-2] //倒數第二頁

如何判斷是吃到哪一個Navigation Controller ?

印出每個controller,每個 controller 設定不同類別
guard let navigationController = navigationController else { return }
navigationController.viewControllers.forEach {
print($0)
}

存取之前畫面的 controller,比方傳資料
guard let navigationController = navigationController else { return }
let count = navigationController.viewControllers.count
let preController = navigationController.viewControllers[count-2]
preController.title = "hello"

//此方法較為不推薦，因為會限制跳轉的頁面固定為第N頁

較好的做法：storyboard?.instantiateViewController(withIdentifier:"DetailViewController") else { return }

pushViewController -> 將畫面加入 (一定要搭配NavigationController)
vc.pushViewController(vc,animated:bool)

如何在跳轉頁面時同時傳遞資料：
跟以前使用相同辦法，在目標頁建立變數 

storyboard?.instantiateViewController(withIdentifier:"DetailViewController") as? t  targetViewController else { return }

轉型為targetViewController -> 如此可將目標頁之變數調來使用

設定不同的Storyboard頁面
let storyboard = UIStoryboard(name:,bundle:)
name -> 想使用的storyboard檔名


Navigation Controller返回上一頁的辦法 -> popToViewController
open func popViewController(animated: Bool) ->UIViewController? 
//回到前一頁
open func popToViewController(_ viewController:UIViewController, animated: Bool) -> [UIViewController]?
//可以指定需要回到哪一頁
open func popToRootViewControllerAnimated(animated: Bool)-> [UIViewController]?
//回到第一頁