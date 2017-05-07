# Errors and exception handling

## Swift
```swift
//1
func canThrowErrors() throws -> String
func cannotThrowErrors() -> String

//2

var vendingMachine = VendingMachine()
vendingMachine.coinsDeposited = 8
do {
    try buyFavoriteSnack(person: "Alice", vendingMachine: vendingMachine)
} catch VendingMachineError.invalidSelection {
    print("Invalid Selection.")
} catch VendingMachineError.outOfStock {
    print("Out of Stock.")
} catch VendingMachineError.insufficientFunds(let coinsNeeded) {
    print("Insufficient funds. Please insert an additional \(coinsNeeded) coins.")
}
//3
func someThrowingFunction() throws -> Int {
    // ...
    return 1
}

let x = try? someThrowingFunction()

let y: Int?
do {
    y = try someThrowingFunction()
} catch {
    y = nil
}
//4
let photo = try! loadImage(atPath: "./Resources/John Appleseed.jpg")
```
#### Code Explanation:
In Swift, errors are represented by values of types that conform to the Error protocol. Enums are one common method of grouping error codes together. There are four ways to handle errors in Swift. You can propagate the error from a function to the code that calls that function(1), handle the error using a do-catch statement(2), handle the error as an optional value(3), or assert that the error will not occur(4). In (1), we indicate that the method can throw an error by using the keyword "throws". A function marked with throws is called a throwing function. In (2), a do-catch block is used to catch errors from a vending machine and print the correct error message. In (3), we can see that you can use try? to handle an error by converting it to an optional value. If an error is thrown while evaluating the try? expression, the value of the expression is nil. In the code in (3) we can see that if someThrowingFunction() throws an error, the value of x and y is nil. Otherwise, the value of x and y is the value that the function returned. Note that x and y are an optional of whatever type someThrowingFunction() returns. Here the function returns an integer, so x and y are optional integers. In (4), we can see that disabling error propogation is done by using a "!" on the try part of the statement. This is done only if you need to disable the errors being thrown by that code.
## PHP
```php
```
#### Code Explanation: