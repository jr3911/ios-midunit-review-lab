## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

** Worked as a pair

Input: `Hello, there`

Output: `HELLO, THERE`

```swift
func hello(_ a: String) -> String {
return a.uppercased()
}
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**

** Worked as a pair

Input: `Hello, there`

Output: `HeLlO, tHeRe`

```swift
var input = "Hello there"
var output: [Character] = Array(input)
var finalString = String()

func final(_ a: String) -> String {
    for i in 0..<output.count {
        if i % 2 == 0 {
            finalString.append(output[i].uppercased())
        } else {
            finalString.append(output[i].lowercased())
        }
    }
    return finalString
}

final(input)
```


3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

```swift
let string = "Hello, there"
var alternateString = String()
for char in string where char != "e" {
alternateString += String(char)
}
```


## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

```swift
let arr = [1,5,2,4,1,4]
let largestNumber = arr.reduce(arr[0], { x, y -> Int in x > y ? x:y })
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`

```swift
let arr = [1,5,2,4,1,4]
let smallestNumber = arr.reduce(arr[0], { x, y -> Int in x < y ? x:y })
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

```swift
let arr = [1,5,2,4,1,4]
let sum = arr.reduce(0,+)
```

4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

```swift
let arr = [3,4.5,7.5,2,1]
let sum = arr.reduce(0,+)
let average = sum / Double(arr.count)
```

5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

```swift
let arr = [3,4.5,7.5,2,1]
let excludedNumber = 3.0

var sum = 0.0
for num in arr where num > excludedNumber {
sum += num
}
```


6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

```swift
let arr = [3,4.5,7.5,2,1]
var product = 1.0

for num in arr {
product = product * num
}
```

7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

```swift
var arr = [3,6,1,9,4,8]
arr.sort()

var secondSmallest = Int()
for num in arr where num != arr[0] {
secondSmallest = num
break
}
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

```swift
var arrOptional = [nil, "We", "come", nil, "in", "peace"]
var arrString = [String]()

for element in arrOptional where element != nil {
arrString.append(element!)
}
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`


## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

** Worked as a pair

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

```swift
var input = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]
var uniqueKeysForDictionary = [String]()

for element in input {
    if uniqueKeysForDictionary.contains(element) == false {
        uniqueKeysForDictionary.append(element)
    }
}
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

** Worked as a pair

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

```swift
var input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

var sortedArray = input.sorted(by: { (s1: String, s2: String) -> Bool in return s1 < s2 })
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

**Worked as a pair

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

```swift
var input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

var sortedArrayByLength = input.sorted(by: { ( s1: String, s2: String) -> Bool in return s1.count < s2.count } )
```

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`


## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

**Worked as a pair

```swift
enum NumberType {
    case even
    case odd

    func evenOrOdd(_ x: [Int]) -> [Int] {
        var answer = [Int]()
        switch self {
        case .even:
            answer = x.filter { (a) -> Bool in
                return a % 2 == 0
            }
        case .odd:
            answer = x.filter { (a) -> Bool in
                return a % 2 == 1
            }
        }
        return answer
    }
}

var input = [1,2,3,4,5,6]

print(NumberType.odd.evenOrOdd(input))
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`



2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

**Worked as a pair

```swift
enum StringType {
    case lowercase
    case uppercase

    func caseSensitive(_ x: String) -> String {
        switch self {
        case .lowercase:
            return x.lowercased()
        case .uppercase:
            return x.uppercased()
        }
    }
}
var caseType = StringType.lowercase
print(caseType.caseSensitive(string))
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

**Worked as a pair

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)

    func extract() -> Int {
        switch self {
        case .saved(let answer):
            return answer
        default:
            return 404
        }
    }

    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}

var input =  [FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)]
var num = 4

var finalArr = [FileStatus]()

for file in input {
    if file.extract() > num {
        finalArr.append(file)
    }
}
print(finalArr)
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
