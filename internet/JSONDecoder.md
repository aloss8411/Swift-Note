要如何將每筆資料存入變數中

->
>利用JSONDecoder ->  可將資料存入所建立之變數中


let decoder = JSONDecoder()
if let weatherData = try? decoder.decode(CurrentWeatherData.self, from: data) {

print("============== Weather data ==============")

print(weatherData)

print("============== Weather data ==============")

}