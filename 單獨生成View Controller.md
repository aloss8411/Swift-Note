
# 產生 storyboard 的 view controller

# # 產生 xib 的 view controller
	利用 controller 的類別名 + ( ) 即可生成 xib 的 view controller。

# 產生完全由程式設計的 view controller
倘若你是個程式控，不喜歡 storyboard & xib，喜歡從程式手刻 controller 畫面的快感，那麼很簡單，搭配 controller 的 init 生成 controller 即可。

	let controller = LoginViewController()
	 
# 產生 segue 連接的 view controller

若我們透過 segue 連接兩個 controller，我們可利用 performSegue 產生 segue 終點的 controller，然後切換到新的 controller 頁面。