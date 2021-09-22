[[Array]]

特點：可容納眾多的資料，並像是字典一樣方便搜尋
		   資料為一組一組的方式進行儲存，像是"name" : "God"
		   每一組以Key & Value的方式進行儲存
		   	key 的型別必須遵從 Hashable protocol,一般是 String
			value 可以是任意型別
			索引的型別須一致,索引對應的資料型別也是
			當Value為Any型別->
				` var book = [String: Any]()
					book["name"] = "大王子"
					book["price"] = 999999`
移除成員：
			
			` var book = ["name":"小王子", "author":"聖修伯里", "price":"300元"]
				book["name"] = nil
			 	let value = book.removeValue(forKey: "author")
				book.removeAll()`
				
Dictionary與Array的結合
				`
					var bookArray1 = [["name":"小王子", "price":"300元"],["name":"小公主"
					, “price":"300元"]
					]
					bookArray1[1]["name"]
				`
				

					var bookArray1 = [

					["money":100,"-":400],["money":200,"-":300]

					]

					bookArray1[1]["-"]
					bookArray1[1]["-"] = 700
					bookArray1[1]["-"]`

每一個格子都用[]包起來，作為判斷陣列的數據
array 的成員是自訂型別，讀取時可用，會自動完成，不容易錯字
				`
					struct Book {
					var name: String
					var price: String
					}

					var bookArray2 = [
					Book(name: "小王子", price: "300元"),
					Book(name: "小公主", price: “300元")
					]
					bookArray2[0].name
				`

				