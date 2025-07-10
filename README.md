# Coding-Challenges
Consist of important coding challenges
## 1 - Write a program for below array whose sum of two numbers = 10
```swift
let array = [3, 6, 2, 7,4]

for i in 0..<array.count {
  for j in (i+1)..<array.count {
    if array[i] + array[j] == 10 {
      print("\(array[i]) + \(array[j]) == 10")
    }
  }
}
```
Output  
3 + 7 == 10  
6 + 4 == 1

## 2(a) - Remove duplicates from Array [Approch Sorted]
```swift
let array = [2,3,4,5,6,1,9,1,3,6,8,9]

var resultArray = [Int]()

for element in array {
    if !resultArray.contains(element) {
        resultArray.append(element)
    }
}
// alter the actaul array
print(resultArray.sorted())
```
Output  
[1, 2, 3, 4, 5, 6, 8, 9]

## 2(b) - Remove duplicates [Approch - Extension]
```swift
extension Array where Element == Int {
  func removeDuplicates() -> [Int] {
    var temparoryArray = [Int]()
     for element in self {
        if !temparoryArray.contains(element){
             temparoryArray.append(element)
          }
    }
    return temparoryArray
  }
}

var array = [3,5,3,4,2,3,4,5,6,7,8,9,5,4]
print(array.removeDuplicates())
```
Output  
[3, 5, 4, 2, 6, 7, 8, 9]  

## 2(c) - Remove duplicates [Generics]

```swift
extension Array where Element: Equatable {
  func removeDuplicates() -> [Element] {
    var temparoryArray = [Element]()
     for element in self {
        if !temparoryArray.contains(element){
             temparoryArray.append(element)
          }
    }
    return temparoryArray
  }
}
var array = [1,3,2,4,5,6,4,3,7,8]
//var array = ["a","b","a","c","d","e"]
print(array.removeDuplicates())

```

Output  
[1, 3, 2, 4, 5, 6, 7, 8] - For numbers  
["a", "b", "c", "d", "e"] - For Strings


## 3(a) - Swap two number's [Approch 1 Math trick]

```swift
var a = 10
var b = 20
print("Before Swap A: \(a) B : \(b)")
a = a + b
b = a - b
a = a - b
print("After Swap A: \(a) B : \(b)")
```
Output  

Before Swap A: 10 B : 20  
After Swap A: 20 B : 10

## 3(b) - Swap two number's [Approch 2 Tuples]

```swift
var a = 10
var b = 20
print("Before Swap A: \(a) B : \(b)")
(a,b) = (b,a)
print("After Swap A: \(a) B : \(b)")
```
Output  

Before Swap A: 10 B : 20  
After Swap A: 20 B : 10

## 3(c) - Swap two number's [Approch 3 Generic's]
```swift
var a = 10.0
var b = 20.0
func swapTwoNumbers<T>( _ a:inout T, _ b: inout T) {
 (a,b) = (b,a)
}
print("Before Swap : A \(a) B : \(b)")
print(swap(&a, &b))
print("After Swap : A \(a) B : \(b)")
```

Output  
Before Swap : A 10.0   B : 20.0  
After Swap : A 20.0   B : 10.0

## 4 - Factorial of given number
```swift
var a = 5
var result = 1

if a < 1 {
  print("A should be greater than 0")
} else {
    while a > 0 {
    result = result * a
    a = a - 1
  }
}
```
Output  
120

## 5 - Swap Index of an array of position 0 & 2

```swift
var numbers = [10,20,30]

func swapIndexOfAnArray<T>(_ array: inout [T], i: Int, j: Int) {
array.swapAt(i, j)
}

print("Before Swap: \(numbers)")
swapIndexOfAnArray(&numbers, i: 0, j: 2)
print("After Swap: \(numbers)")
```
Output  
Before Swap: [10, 20, 30]  
After Swap: [30, 20, 10]

