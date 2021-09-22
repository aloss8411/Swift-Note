沒有 segue 時,傳資料到下一頁的方法
• 產生 controller
• 將資料存入 controller 的 property
• 利用 pushViewController,present 或show 顯示 controller

navigationController?.pushViewController(controller, animated:
true)
present(controller, animated: true, completion: nil)
show(controller, sender: nil)


Example:
guard let controller =storyboard?.instantiateViewController(withIdentifier: "\
(DetailViewController.self)") as? DetailViewController else{ return }
controller.color = UIColor.red

如何從程式切換頁面

• 不靠 segue
• 呼叫 navigation controller 的 pushViewController(_:animated:)
• 呼叫 UIViewController 的 present(_:animated:completion:)
• 呼叫 UIViewController 的 show(_:sender:)
• 自動依據是否有 navigation controller,決定要用 push 還是
present

• 靠 segue
• 呼叫 performSegue(withIdentifier:sender:)
• 定義 shouldPerformSegue(withIdentifier:sender:)