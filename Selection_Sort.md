# Сортировка выбором
Суть данного алгоритма заключается в том, что мы идём по элементам слева направо (от 0 элемента к последнему), и ищем среди оставшихся элементов самый большой. 
Если находим, то меняем местами элемент, на котором мы сейчас и самый большой элемент. 
```
func selectionSort(_ array: inout [Int]) {
    let n = array.count
    guard n > 1 else {return}
    
    for i in 0..<n {
        var minIndex = i
        for j in (i + 1)..<n {
            if array[j] < array[minIndex] {
                minIndex = j
            }
        }
        if minIndex != i {
            array.swapAt(i, minIndex)
        }
    }
}
// Пример использования
var numbers = [5, 3, 6, 2, 10]
print("Исходный массив: \(numbers)")
selectionSort(&numbers)
print("Отсортированный массив: \(numbers)")

```
