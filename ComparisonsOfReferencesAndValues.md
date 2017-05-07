# Comparisons of references and values 

## Swift
```swift
let a = "Dale"
let b = "Dale"

if a == b {
    print("they equal")
}else{
    print("invalid comparison")
}
```
#### Code Explanation:
Output: "They are equal"
This code declares two strings of the same value. An if else statement then uses the == operator to see if the strings are of the same value. In Swift, Strings are a value type. Since the value of both of the strings is the same, the if statement is true and exectues the print statement declaring they are equal.

### How are values compared? (i.e. comparing two strings)
When comparing two strings we see that Swift’s String type is a value type. If you create a new String value, that String value is copied when it is passed to a function or method, or when it is assigned to a constant or variable. In Swift, using the '==' operator allows you to compare if two strings are the same. Swift also includes several methods of comparing strings using functions like the .contains() function.

## PHP
```php
```
#### Code Explanation:

### How are values compared? (i.e. comparing two strings)