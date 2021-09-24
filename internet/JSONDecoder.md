要如何將每筆資料存入變數中

->
>利用JSONDecoder ->  可將資料存入所建立之變數中

>CurrentWeatherData.self ->參數 type 傳入想要生成的東⻄的型別,傳入型別的寫法是型別名字加
上 .self 。 傳入 CurrentWeatherData.self,因此常數 CurrentWeatherData 的型
別將是 SearchResponse

let decoder = JSONDecoder()
if let weatherData = try? decoder.decode(CurrentWeatherData.self, from: data) {

print("============== Weather data ==============")

print(weatherData)

print("============== Weather data ==============")

}