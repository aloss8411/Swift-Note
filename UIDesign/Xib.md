xib 可設計 App 裡常出現的 UI 元件,方便重覆利用,比方 loading view
*不可以拉Segue

建立起Xib檔案後，在所需ViewController中加入
> Bundle.main.loadNibNamed( ,owner:,option:)

->[array] >意思為在該Xib檔案中將物件作為Array儲存

應用：建立一個Class，繼承自Xib檔案 
並利用上述宣告，即可於各ViewController中客製化相關內容及應用

#todo 
- [x] test
- [ ] 