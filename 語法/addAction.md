# 設定某事件觸發的程式 — addAction(_:for:)

剛剛介紹的例子都在產生元件時傳入 UIAction，UIAction 的 closure 程式將在元件的主要事件發生時觸發，也難怪參數的名字叫 primaryAction。

那如果我們想設定其它事件呢 ? 比方 UITextField 的 editingDidEndOnExit，return 鍵按下的事件呢 ?

我們可以透過 `addAction(_:for:)` 加入對應某事件的 UIAction。

func addAction(_ action: UIAction, for controlEvents: UIControl.Event)