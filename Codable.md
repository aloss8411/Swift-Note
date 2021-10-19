編碼：
let encoder = JSONEecoder()
guard let data = try? encoder.encode(lovers) else { return }

解碼
let decoder = JSONDecoder()
guard let data = try? decoder.decode(xxx.self)else{return}