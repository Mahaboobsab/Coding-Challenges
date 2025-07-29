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

---- OR ----
let array = [3, 6, 2, 7, 4]
var seen = Set<Int>()
for num in array {
    let complement = 10 - num
    if seen.contains(complement) {
        print("Element \(complement) + Element \(num) == 10")
    }
    seen.insert(num)
}

```
**Output**  

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
**Output**  

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
**Output**  

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

**Output**  

[1, 3, 2, 4, 5, 6, 7, 8] - For numbers  
["a", "b", "c", "d", "e"] - For Strings

## 2(d) - Remove duplicates of an array [Approch - Mutating]
```swift
extension Array where Element: Equatable {
 mutating func removeDuplicates() {
    var temparoryArray = [Element]()
     for element in self {
        if !temparoryArray.contains(element){
             temparoryArray.append(element)
          }
    }
    // Assigning to itself
    self = temparoryArray
  }
}
var array = [1,3,2,4,5,6,4,3,7,8]
//var array = ["a","b","a","c","d","e"]
array.removeDuplicates()
print(array)
```
**Output**  

[1, 3, 2, 4, 5, 6, 7, 8]

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
**Output**  

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
**Output**  

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

**Output**  

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
**Output**  

120  

## Recusrion Approch


```swift
/*
func factorial(n : UInt64) -> UInt64 {
  return n < 2 ? 1 : n * factorial(n: (n-1))
}

print(factorial(n: 5))

*/
/*
func factorial(n: UInt64) -> UInt64 {
    print("Calling factorial(\(n))")
    
    if n < 2 {
        print("Reached base case: factorial(\(n)) = 1")
        return 1
    } else {
        let result = n * factorial(n: n - 1)
        print("Computed factorial(\(n)) = \(result)")
        return result
    }
}

print("Final Result: \(factorial(n: 5))")
*/
```

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
**Output**  

Before Swap: [10, 20, 30]  
After Swap: [30, 20, 10]

## 6(a) - Find the capital leeters in a given string [Approch 1]
```swift
//Find capital letters

let nameStr = "Meheboob R Nadaf"

func removeDuplicateCharacters(str: String) -> [Character] {
var characters = [Character]()

for char in str {
  if char >= "A" && char <= "Z" {
    characters.append(char)
  }
}
return characters
}

let x = removeDuplicateCharacters(str: nameStr)
print(x)
```
**Output**  

["M", "R", "N"]

## 6(b) - Find the capital leeters in a given string [Approch 2 Higher order function]
```swift
let nameStr = "Meheboob R Nadaf"

let xx = nameStr.filter({
  ("A"..."Z").contains($0)
})

print(xx)
```
**Output**  

MRN

## 7 - Fing how many time the character repeats in a give string
```swift
let name = "hello world"
var dict = [Character: Int]()

for char in name {
  if let i =  dict[char] {
    dict[char] = (i + 1)
  } else {
    dict[char] = 1
  }
}

for (char, count) in dict {
  print("Char \(char) repeats \(count) times")
}
```
**Output**  

Char r repeats 1 times  
Char l repeats 3 times  
Char o repeats 2 times  
Char h repeats 1 times  
Char e repeats 1 times  
Char w repeats 1 times  
Char d repeats 1 times  
Char   repeats 1 times

## 8: Reverse String

```swift
import Foundation
let name = "Nadaf"
let reversed = String(name.reversed())
print(reversed)
```

**Output**  

fadaN

## 9: Add missing code & handle success & empty resonse scenario in below  
```swift
Add missing code in below class and write test case to handle empty response as well

import Foundation


let jsonData: String = """
[{"id": 1, "name": "Lilly", "surname": "Polo", "imageurl": "https://randomuser.me/api/portraits/women/21.jpg"},
{"id": 2, "name": "Andy", "surname": "Polo", "imageurl": "https://randomuser.me/api/portraits/women/21.jpg"},
]
"""

enum APIError: Error, Equatable {
    case invalidData
    case notFoud
    case failure
}


struct APIManager {
    func getUserList(compltion: @escaping ([User]?, APIError?) -> Void) {
        let data = jsonData.data(using: .utf8)
        guard let data = data else {
            compltion(nil, APIError.failure)
            return
        }
        do {
            let userList = try JSONDecoder().decode([User].self, from: data)
            compltion(userList, nil)
        } catch {
            compltion(nil, APIError.invalidData)
        }
    }
}

struct User: Codable {
    let id: Int
    let name: String
    let surname: String
    let imageurl: String
}

struct UserViewModel {
 func fetchUserList(completion: @escaping ([User]?, APIError?) -> Void) {
        APIManager().getUserList(compltion: completion)
    }
}
```
Ans:  
```swift
struct UserViewModel {
    private let apiManager: APIManagerProtocol

    init(apiManager: APIManagerProtocol = APIManager()) {
        self.apiManager = apiManager
    }

    func fetchUserList(json: String = jsonData, completion: @escaping ([User]?, APIError?) -> Void) {
        apiManager.getUserList(json: json, completion: completion)
    }
}

protocol APIManagerProtocol {
    func getUserList(json: String, completion: @escaping ([User]?, APIError?) -> Void)
}

struct APIManager: APIManagerProtocol {
    func getUserList(json: String = jsonData, completion: @escaping ([User]?, APIError?) -> Void) {
        guard let data = json.data(using: .utf8) else {
            completion(nil, .failure)
            return
        }
        do {
            let userList = try JSONDecoder().decode([User].self, from: data)
            completion(userList, nil)
        } catch {
            completion(nil, .invalidData)
        }
    }
}

class MockAPIManager: APIManagerProtocol {
    var mockUsers: [User]?
    var mockError: APIError?

    func getUserList(json: String, completion: @escaping ([User]?, APIError?) -> Void) {
        completion(mockUsers, mockError)
    }
}

func testFetchUserList_withMock_shouldReturnExpectedUsers() {
    let mockManager = MockAPIManager()
    mockManager.mockUsers = [
        User(id: 1, name: "Test", surname: "User", imageurl: "https://example.com/image.jpg")
    ]
    mockManager.mockError = nil

    let viewModel = UserViewModel(apiManager: mockManager)

    let expectation = self.expectation(description: "Mock user list")

    viewModel.fetchUserList { users, error in
        XCTAssertNil(error)
        XCTAssertNotNil(users)
        XCTAssertEqual(users?.count, 1)
        XCTAssertEqual(users?.first?.name, "Test")
        expectation.fulfill()
    }

    waitForExpectations(timeout: 1, handler: nil)
}

func testFetchUserList_withMockSuccess_shouldReturnExpectedUsers() {
    let mockManager = MockAPIManager()
    mockManager.mockUsers = [
        User(id: 1, name: "Lilly", surname: "Polo", imageurl: "https://randomuser.me/api/portraits/women/21.jpg"),
        User(id: 2, name: "Andy", surname: "Polo", imageurl: "https://randomuser.me/api/portraits/women/21.jpg")
    ]
    mockManager.mockError = nil

    let viewModel = UserViewModel(apiManager: mockManager)
    let expectation = self.expectation(description: "Success response")

    viewModel.fetchUserList { users, error in
        XCTAssertNil(error)
        XCTAssertNotNil(users)
        XCTAssertEqual(users?.count, 2)
        XCTAssertEqual(users?[0].name, "Lilly")
        XCTAssertEqual(users?[1].name, "Andy")
        expectation.fulfill()
    }

    waitForExpectations(timeout: 1, handler: nil)
}

func testFetchUserList_withMockEmptyResponse_shouldReturnEmptyArray() {
    let mockManager = MockAPIManager()
    mockManager.mockUsers = []
    mockManager.mockError = nil

    let viewModel = UserViewModel(apiManager: mockManager)
    let expectation = self.expectation(description: "Empty response")

    viewModel.fetchUserList { users, error in
        XCTAssertNil(error)
        XCTAssertNotNil(users)
        XCTAssertEqual(users?.count, 0)
        expectation.fulfill()
    }

    waitForExpectations(timeout: 1, handler: nil)
}
```
## 10: Sum of a given number from 1

```swift
import Foundation

func getSumOfNumberFromOne( number:  Int) -> Int {
    
//    var result = 0
//    var num = number
//
//    while num > 0 {
//        result = result + num
//        num -= 1
//    }
//
//    return result
    
    return number * (number + 1) / 2
}

var num = 5
print(getSumOfNumberFromOne(number: num))
```
**Output**  

15

## 11: Fibonanci of a given number  

```swift
func fibonacci(upTo n: Int) -> [Int] {
    guard n > 1 else { return [0] }

    var sequence = [0, 1]
    while sequence.count < n {
        let next = sequence[sequence.count - 1] + sequence[sequence.count - 2]
        sequence.append(next)
    }
    return sequence
}

print(fibonacci(upTo: 10))
```

## 12: Reverse String without reversed() built in function

```swift
func reverseString(_ input: String) -> String {
    var reversed = ""
    for char in input {
        reversed = String(char) + reversed
        print(reversed)
    }
    return reversed
}

// Test
let original = "hello"
let reversed = reverseString(original)
print("Original: \(original)")
print("Reversed: \(reversed)")
```

----  O/P----  
Original: hello  
Reversed: olleh  

## 13: Reverse Array without reversed() built in function  

```swift
func reverseArray(_ arr: [Int]) -> [Int] {
    var reversed: [Int] = []
    for element in arr {
        reversed.insert(element, at: 0)
    }
    return reversed
}

// Test
let original = [1, 2, 3, 4, 5]
let reversed = reverseArray(original)
print("Original: \(original)")
print("Reversed: \(reversed)")
```

----O/P----  
Original: [1, 2, 3, 4, 5]  
Reversed: [5, 4, 3, 2, 1]

## 14: Reverse a give number  

```swift
func reverseNumber(_ num: Int) -> Int {
    var number = num
    var reversed = 0

    while number != 0 {
        let digit = number % 10          // Get the last digit
        reversed = reversed * 10 + digit // Append digit to reversed number
        number /= 10                     // Remove the last digit
    }

    return reversed
}

// Test
let original = 12345
let reversed = reverseNumber(original)
print("Original: \(original)")
print("Reversed: \(reversed)")
```
