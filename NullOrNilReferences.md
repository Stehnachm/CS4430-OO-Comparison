# Null/nil references

## Swift
```swift
var shawn: String?

shawn = "shawn"

print(shawn ?? "bad")

shawn = nil

print(shawn ?? "bad")
```
#### Code Explanation:
Output: Shawn bad

In this block of code, a variable named shawn of type String Optional(?) is declared. Shawn is then set to the string "shawn" and printed. Shawn is then set to nil and printed. Using the nil-coalescing the print statement will return the value of the string if it is not nil and will return "bad" if it is nil. In this case shawn is bad. 
### Which does the language use? (null/nil/etc)
Swift uses nil. It is interesting to point out that Swift's nil is not the same as nil in Objective-C. In Objective-C, nil is a pointer to a non-existent object. In Swift, nil is not a pointer—it is the absence of a value of a certain type.
### Does the language have features for handling null/nil references?
In Swift we have something called "Optionals". Optionals are denoted by a ? and they are used to handle the absense of a value. Apple documentations says, "Optionals say either there is a value, and it equals x or there isn’t a value at all." One of the core features of swift as a language is optionals and how they are used to handle nil values.

Optionals also have the ability to be "unwrapped", which means that they can be passed around with a nil value inside of them or an appropriate value, but still satisfy the parameters of various functions.
## PHP
### Which does the language use? (null/nil/etc)
The word 'NULL' is used to signify a variable with no value in PHP. A value will be considered to be NULL if any of the following are true:
- The variable has been assigned to the constant NULL
- The variable has not yet been assigned a value
- The variable has been unset using the unset() function

### Does the language have features for handling null/nil references?
The easiest way to do this in PHP is to either use the '===' comparison operator or to use the function is_null().

This code example illustrates some of the usages of NULL:
```
<?php
    $a = NULL;    
    if (is_null($a)) echo "a is null, ";
    
    $b;    
    if($b === NULL) echo "b is null, ";
    
    $c = 42;
    unset($c);
    if($c === NULL) echo "c is null";
?>
```
#### Code Explanation:
At the end of this segment of code, all three variables are NULL. The different ways to consider whether or not the variables are NULL are also shown. The output of the code would be "a is null, b is null, c is null".
