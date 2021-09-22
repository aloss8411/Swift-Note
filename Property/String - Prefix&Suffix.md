let numbers = [1, 2, 3, 4, 5]
print(numbers.prefix(2))
// Prints "[1, 2]"
print(numbers.prefix(10))
// Prints "[1, 2, 3, 4, 5]"

常用於抓取字串中第一個字母

let day = "day"
print(day.suffix[2])
//answer = ay
let month = "month"
print(month.suffix[4])
//answer = onth

swift 3中抓取第一個字母範例
`
extension String {
    func capitalizingFirstLetter() -> String {
        let first = String(characters.prefix(1)).capitalized
        let other = String(characters.dropFirst())
        return first + other
    }

    mutating func capitalizeFirstLetter() {
        self = self.capitalizingFirstLetter()
    }
}
SWIFT 4.0

Extension String {
    func capitalizingFirstLetter() -> String {
      return prefix(1).uppercased() + dropFirst()
    }

    mutating func capitalizeFirstLetter() {
      self = self.capitalizingFirstLetter()
    }
`
