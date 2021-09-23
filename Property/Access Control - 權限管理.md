權限管理


在 Swift 中可分為 5 個層級。層級最高到最低依次為 open / public / internal / file-private / private。層級最高表示限制最少，反之表示限制最多。  
1.open：  
只用於 class 宣告以及 class 內所有的成員宣告。所有 module 和 source file 都可取得，可讓繼承者繼承此 class 和 override 此 class 內的 method。  

2.public：  
不限用於 class，所有 module 和 source file 都可取得。但若為 class，則繼承者不可繼承此 class 和override 其 method。  

3.internal：  
宣告於 module 內所有 source file 才可取得，於 module 外無法取得。module 內所有source file，若為class，可讓繼承者繼承此 class 和 override 此 class 內的 method。同時，此為預設的 access control，也就代表預設的存取權限只能用於你寫的 module 內，在 module 外無
法取得。  

4.fileprivate：  
宣告的 source file 內才可取得，若為 class，可讓繼承者繼承此 class 和 override 此 class 內的 method。  

5.private ：  
宣告的區塊內才可取得，也就是大括號內才可取得。若為 class，可讓繼承者繼承此 class 和 override 此 class內的 method。


[var]
[let]