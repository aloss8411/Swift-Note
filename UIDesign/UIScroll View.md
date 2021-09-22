dfs [[UIPageControl]] 
 
 特點：
  scroll view 本身的大小由 frame 決定，但內容的大小則由 content size 決定
 
 
 設立一Scroll View，並另外設置一View(同一ViewController中)放置內容
-   設定Scroll View&View的長寬比例
-   調整View的X,Y部分
-   於Runtime Attribute階段添加contentSize，並設定長寬
    -   注意要點 View長度需大於Scroll View的長度
-   分頁功能：勾選Page Enabled
    -   分頁的大小由Scroll View決定


>如何判斷目前到什麼地方？ 
	將ScrollView設定Delegate給ViewController並遵從UIScrollViewDelegate(可用Extension)
	接著使用func scrollViewDidEndDecelerating(_ scrollView: UIScrollView) {  } ->將在畫面停止滑動時呼叫，並判斷目前頁數：scrollView.contentOffset.x / scrollView.bounds.width

-> scrollView.contentOffset.x 則是目前滑動的水平距離


縮放功能：
				![[Pasted image 20210901221756.png]]
				![[Pasted image 20210901221923.png]]
>ScrollViewDelegate底下的viewForZooming控制放大縮小功能	
extension ViewController: UIScrollViewDelegate {  
func viewForZooming(in scrollView: UIScrollView) -> UIView? {  
	imageView  
	} 
}				
>延伸
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-scroll-view-縮放圖片-72960fb1b332
				


參考資料：
https://medium.com/彼得潘的試煉-勇者的-100-道-swift-ios-app-謎題/scroll-view-delegate-練習-60e185298513




如何決定捲動範圍 -> 由子圖決定母圖的範圍
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/scroll-view-決定捲動範圍的-content-layout-guide-6f606740918a

frame layout guide 代表 scroll view 本身 frame 的框框
scroll view 本身的大小由 frame 決定，但內容的大小則由 content size 決定

ScrollView的浮動元件
https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/利用-scroll-view-的-frame-layout-guide-設計浮動元件-805f935e1877