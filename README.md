import UIKit

/*1 

func isEven(a: Int) -> Bool {
    if a % 2 == 0 {
        return true
    } else {
        return false
    }
}

 2
 
func isDividableBy(a: Int, b: Int) -> Bool {
    return a % b == 0
}
isDividableBy(a: 6, b: 4)

3
 
var array = [Int]()
for value in 0...100 {
    array.append(value)
}

print(array)

4

var array = Array(0...100)

var index = 0
while index < array.count {
    if array[index] % 2 == 0 || array[index] % 3 != 0 {
        array.remove(at: index)
        index -= 1
    }
    index += 1
}

print(array)

5
 
func fiboArray(count: Int) -> [Int] {
     var tempArray = [0,1]

    for index in 2...count {
        tempArray.append(tempArray[index - 2] + tempArray[index - 1])
}

    return tempArray
}

print(fiboArray(count: 45))*/

let max = 100
var set = Set<Int>(5...max)

var index = 2

for value in set {
    while value * index <= max {
        set.remove(value * index)
        index += 1
    }
    index = 2
}

print(set)
