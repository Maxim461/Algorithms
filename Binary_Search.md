# Бинарный поиск
Пример: игра "угадай число". Загадано число от 1 до 100. При каждой попытке возвращается ответ: "мало", "много" или "угадал". Плохой способ – перебирать все числа подряд. 
При самом отрицательном сценарии потребуется 100 попыток. Эффективный способ – начнем с 50. Если мало, то пробуем 75. Если много, то 63 и тд, каждый раз исключая половину оставшихся возможных вариантов. 
Какое бы число не было задумано, его можно угадать не более чем за 7 попыток.
```
func binarySearch(_ array: [Int], target: Int) -> Int? {
    var low = 0
    var high = array.count - 1
    
    while low <= high {
        let mid = (low + high) / 2
        let guess = array[mid]
        
        if guess == target {
            return mid
        } else if guess > target {
            high = mid - 1
        } else {
            low = mid + 1
        }
    }
    
    return nil
}

// Пример использования
let array = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
let target = 13
if let index = binarySearch(array, target: target) {
    print("Элемент найден в индексе", index)
} else {
    print("Элемент не найден")
}
```
