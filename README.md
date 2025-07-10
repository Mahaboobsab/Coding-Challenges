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
