https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/使用-cocoapods-管理第三方套件-6e6135b62814

打開terminal ->


第一步：找到資料位置

輸入cd + 空白 後面拖曳藍色Project 至後面並刪除Xcodeproj

第二步：建立Profile

輸入pod init ，此時會跳出類似text檔，在# pod for xxx下描述想添加的cocoapods

For Example:
# Pods for Demo  
pod 'Kingfisher'