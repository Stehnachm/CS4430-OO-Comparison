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
As of version 5.3, PHP supports lambdas and closures. Lambdas are created by simply assigning an anonymous function to a variable name. They can be then be passed as arguments to other functions. 

A closure is implemented by the "use" keyword to increase the scope of a lambda to include other variables. 
```php
<?php
    $max_comparator = function ($max) {
      return function ($v) use ($max) { return $v > $max; };
    };

    $input = array(1, 2, 3, 4, 5);
    $output = array_filter($input, $max_comparator(2));
?>
```
#### Code Explanation:
Here the variable max_comparator is a lambda that is used with the array_filter function to compare the variables of an input array to see if they fit a certain criteria. This criteria is defined in another anonymous function within max_comparator that makes use of closures, requiring that the number be over a value specified by the user when calling the function. 

In this code, the output variable would include the following:

[3,4,5]