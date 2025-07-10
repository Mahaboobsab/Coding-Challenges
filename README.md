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

## 2 - Remove duplicates from Array
```swift
let array = [2,3,4,5,6,1,9,1,3,6,8,9]

var resultArray = [Int]()

for element in array {
    if !resultArray.contains(element) {
        resultArray.append(element)
    }
}
print(resultArray.sorted())
```
Output  
[1, 2, 3, 4, 5, 6, 8, 9]

## 3 - Swap two number's [Approch 1 Math trick]

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

## 4 - Swap two number's [Approch 2 Tuples]

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

## 5 - Swap two number's [Approch 3 Generic's]
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
