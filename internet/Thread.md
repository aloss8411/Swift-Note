每個 thread 可執行不同的程式,做不同的事。當iOS App 執行時,一開始就會產生多個 thread,每
個 thread 做不同的事情。
• 可以把 thread 想成執行程式的人。
• iPhone 有多個 CPU,可同時做不同的事。因此多個thread 可分配到不同 CPU 同時做事或是快速切換輪流做事,讓效能更好,程式更快跑完。

>main thread
• 主要的 thread,負責比較重要,要優先處理的事,比方 UI 相關操作就是它負責

> background thread
• 負責比較不重要的事,比方下載網路上的資料,可以在背後下載,不影響使用者的操作

檢查是否是main thread
print(Thread.isMainThread)