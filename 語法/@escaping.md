@escaping 是個讓 closure 在 function 外繼續使用的特別語法。它有點難懂，但你卻不能忽略，因為 iOS SDK 裡不少 function 的參數都加了 @escaping

> 副作用 : @escaping 幫我們解決問題，但也帶來一些副作用，就像止痛藥一樣。例如以下例子，當你想在 closure 的 { } 裡存取物件自己的屬性或方法時，必須額外加上 self，



https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/讓-closure-在-function-外繼續使用的-escaping-40d50b17f75b

function中的參數若是optional -> swift自動預設為帶有@escaping


@escaping作用：讓Closure能在逃脫Function，在func外使用