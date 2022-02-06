在程式中檢查 iOS 版本的方法有以下三種:

-   方法 1: #available
-   方法 2: #unavailable
-   方法 3: @available


方法 1: #available

#available 可搭配 if，guard & while。以下例子的 `if #available(iOS 15.0, *)` 表示 iOS 15 以上(包含 15) 採用 if { } 裡的 AsyncImage，iOS 15 之前的版本採用 else { } 裡的寫法。

那`#available()` 裡的 * 是什麼意思呢 ? 它表示其它沒有在 ( ) 裡提到的平台採用 if { } 裡的寫法，因此 macOS，watchOS 等平台將採用 if { } 裡的寫法。

若是 App 只支援 iOS，只設定 iOS 版本的限制是 ok 的，因為 App 不會跑在其它的平台。如果想支援更多平台，比方想支援 Apple Watch，剛剛的程式須同時加入 iOS & watchOS 的版本限制，因為 watchOS 8 以上才支援 AsyncImage。


方法 2:#unaviailable

－主要針對舊版OS設定，避免純粹為了舊版而設定撰寫過多程式

那`#available()` 裡的 * 是什麼意思呢 ? 它表示其它沒有在 ( ) 裡提到的平台採用 if { } 裡的寫法，因此 macOS，watchOS 等平台將採用 if { } 裡的寫法。

若是 App 只支援 iOS，只設定 iOS 版本的限制是 ok 的，因為 App 不會跑在其它的平台。如果想支援更多平台，比方想支援 Apple Watch，剛剛的程式須同時加入 iOS & watchOS 的版本限制，因為 watchOS 8 以上才支援 AsyncImage。

`if #unavailable(iOS 15.0) { }`

方法 3:@aviailable

@available 也可以檢查版本，( ) 裡的寫法跟 #available 類似，不過它只能單獨寫，不能搭配 if，guard & while，因此它通常加在型別定義或 function & 變數的宣告前，例如以下例子表示只在 iOS 15 以上版本(包含 15)定義 ContentView。