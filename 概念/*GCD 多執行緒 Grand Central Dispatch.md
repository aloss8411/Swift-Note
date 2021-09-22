GCD為多執行緒的運用，其作用在於可將單一任務拆成多個小任務同時執行，亦或者同時執行多個任務，目的在於縮短執行任務的時間，而最重要的是，要確保不要佔用主執行緒而影響到使用者的體驗。

>特點
App 執行時,多個 thread 執行不同的程式碼。
• thread 分為 main thread & background thread。main thread priority 最高,最優先執行
• iOS 將產生多個 queue,每個 queue 裡排隊的是我們想要執行的程式碼。
• 系統從 queue 裡取出要執行的程式碼,分配給某個 thread 執行。
• Queue 有不同的 priority,main queue 的 priority 最高,從 main queue取出的程式碼會分配給 main thread 執行。
• 網路抓資料之類花時間的工作,應該在 background thread 做,如果在main thread 做會卡住 UI。



>Queues:

queues 是資料結構中的一種型態，翻成中文叫「佇列」。它的特性是先進先出(FIFO, First-in First-out)

>Serial vs Concurrent

Serial :

serial queues 的意思就是這個佇列裡的工作是按照順序執行的，一次只執行一個，當前一個執行完後，才會執行下一個。serial queues 適合拿來處理共享的資源，因為這樣可以確保存取是按照順序來的。

Concurrent :

相對於 serial 就是同時發生的。也是說多個工作是同時被執行的。concurrent queues 代表這個 queues 裡的工作會按順序「開始」執行，但因為是 concurrent ，所以不必等上一個工作執行完才接著執行下一個，因此每個工作執行結果的時間是不可預測的


GCD研究
https://franksios.medium.com/ios-gcd多執行緒的說明與應用-c69a68d01da1