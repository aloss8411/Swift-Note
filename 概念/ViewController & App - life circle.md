ViewControllers:
•UIViewController 定義很多畫面出現 / 消失時會被觸發的 function
• 由系統自動呼叫,不是我們自己呼叫

畫面出現＆消失時會出現的六種View Controller methods

• func loadView()

• func viewDidLoad()
controller 的畫面完成載入時呼叫,只會呼叫一次,適合做初始化的工作,設定畫面一開始呈現的內容
• func viewWillAppear(_ animated: Bool)
每次畫面現身都被呼叫,但畫面還未出現。若做太多事將卡住畫面。
• func viewDidAppear(_ animated: Bool)
每次畫面現身都被呼叫,畫面出現後呼叫。
• func viewWillDisappear(_ animated: Bool)

• func viewDidDisappear(_ animated: Bool)
	
	
	記得以 super 呼叫父類別的 function
	
	
App :

![[Pasted image 20210912154221.png]]

App之代理人為UIApplication 

AppDelegate &UIApplicationDelegate

•UIApplicationDelegate 宣告了在 App 的重要時刻會被觸發的 method
• 定義這些 method 的 AppDelegate 物件是App 的代理人

@main ->被建立為AppDelegate物件作為代理人

第一次啟動時會觸發
 func application(_ application: UIApplication,didFinishLaunchingWithOptions launchOptions:[UIApplication.LaunchOptionsKey: Any]?) -> Bool {
return true
}
->一生一次,適合做一些一次性,App 初始化的動作,比方設定 App 元件的顏色,抓取網路資料等

->可能適用場景
1.使用者主動重新啟動 App
2. 使用者點選 App Icon 讓之前啟動的 App 回到前景,但由於 App 在背景被系統殺掉,
所以等同於重新啟動 App
3.使用者點選推播,啟動 App
4.被別的 App 啟動

App 死亡觸發的func applicationWillTerminate(_ application:UIApplication)

SceneDelegate &UISceneDelegate

作為代替UIWindow的代替品

• iOS 13 開始,App 執行後可有多個 scene,每個scene 可以有多個 window
• scene 有 delegate,型別是 UISceneDelegate
• scene 進入前景 / 背景時將觸發 delegate 的相關method

scene(willConnectTo:options:) ->當 App 啟動,scene (window) 即將產生時呼叫

適合做一些初始化的動作,
比方抓取網路資料,設定畫面的主要顏色等

sceneDidEnterBackground()
•儲存重要資料
倘若 App 不幸突然死亡,下次啟動 App,資料還會存在。

• 移除用不到的物件
佔用更少記憶體,減少被殺的機率。ex: 移除UI元件

記得在 sceneWillEnterForeground() 裡還原
sceneDidEnterBackground()

sceneWillEnterForeground(_:) //進入前景
sceneDidBecomeActive(_:) //進入active狀態


//詳解
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/1-2-app-anatomy-and-life-cycle-develop-in-swift-data-collections-重點整理-cdbff33408df