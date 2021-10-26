可放置一些常用的物件或選項，例如說建立起menu

利用propertyListDecoder來解析plist

自New File建立起一個新的plist，並建立所需要的資料型態

>利用 PropertyListDecoder 析解 plist

let url = Bundle.main.url(forResource: "Drinks", withExtension: "plist")!  
  
if let data = try? Data(contentsOf: url), let drinks = try? 	PropertyListDecoder().decode([Drink].self, from: data) {  
print(drinks)  
}