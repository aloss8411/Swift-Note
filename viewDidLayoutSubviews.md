# viewDidLayoutSubviews
當使用 auto layout 設計畫面時，元件要等到 viewDidLayoutSubviews 才會變成真正的位置大小

所以什麼時候才能取得元件真正的位置大小呢 ? 要等到 view controller 的 function viewDidLayoutSubviews 執行時。

override func viewDidLayoutSubviews() {  
        super.viewDidLayoutSubviews()  
        print(imageView.frame)  
}