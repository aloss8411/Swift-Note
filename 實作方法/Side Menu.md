https://medium.com/彼得潘的-swift-ios-app-開發教室/swift-ios練習-side-menu-e10b088744dc


youtube解說
https://www.youtube.com/watch?v=B5-1_aR20rE

使用addchild 函式做出效果
-> 會利用到prepare
      

 
 
 //第二種製作方式
 https://johncodeos.com/how-to-create-a-side-menu-in-ios-using-swift/
 
 
 建立出所需要的母視圖與子視圖
 
 
 Code:
 
      
var sideMenu = sideMenuViewController()
      
 addChild(sideMenu)

 view.insertSubview(sideMenu.view, at: 2)

 sideMenu.didMove(toParent:self)
 
 若需要像Side Menu一樣，則設定原先Parent View 及 childView之移動方式即可達成