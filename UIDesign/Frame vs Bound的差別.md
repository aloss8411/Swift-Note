Frame vs Bound的差別  
Frame是相對於Super view的位置大小
Bound則是相對於自己的位置及大小
也就是說先用Frame定義元件相對於SuperView的位置及大小，再利用Bounds客製化想要的位置及大小。
可利用UIScreen.main.bounds or UIScreen.main.nativeBounds取得尺寸
nativebounds & bounds皆可以取得螢幕大小，但有些許不同
nativebounds : 以pixel為單位，且永遠回傳直向尺寸