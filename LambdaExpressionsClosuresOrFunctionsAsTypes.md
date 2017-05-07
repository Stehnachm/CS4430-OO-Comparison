# Lambda expressions, closures, or functions as types

## Swift
```swift
let names = ["Chris", "Alex", "Ewa", "Barry", "Daniella"]

func backward(_ s1: String, _ s2: String) -> Bool {
    return s1 > s2
}
var reversedNames = names.sorted(by: backward)
```
#### Code Explanation:
Output:
["Ewa", "Daniella", "Chris", "Barry", "Alex"]. 

Closures are used in swift. In the above code we can see that the function "backward()" uses a closure in order to return the strings in the opposite order. These are comparable to lambda expressions in some other languages. Closures are self-contained blocks of functionality that can be passed around and used in your code. Closures are a convenient means of naming and defining self-contained blocks of code as part of a larger function. However, it is sometimes useful to write shorter versions of function-like constructs without a full declaration and name. This is particularly true when you work with functions or methods that take functions as one or more of their arguments.
## PHP
```php
```
#### Code Explanation: