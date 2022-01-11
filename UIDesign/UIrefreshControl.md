下拉時可更新資料

func configureRefreshControl () 
{ // Add the refresh control to your UIScrollView object. myScrollingView.refreshControl = UIRefreshControl() myScrollingView.refreshControl?.addTarget(self, action: #selector(handleRefreshControl), for: .valueChanged)} @objc func handleRefreshControl() { // Update your content…  // Dismiss the refresh control. DispatchQueue.main.async { self.myScrollingView.refreshControl?.endRefreshing() }}

