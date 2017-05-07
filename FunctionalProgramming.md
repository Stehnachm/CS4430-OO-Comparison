# Functional programming

## Swift
```swift
let addFive = { $0 + 5 }
print(addFive(7))
//Hello Dale
```
#### Code Explanation:
Output: 12

Swift supports functional programming. In the above code we can see a demonstration of a function as a first class citizen. The code declares a function "addFive" that adds 5 to whatever number is passed in to the function.
### Does the language support functional programming?
Yes, Swift supports functional programming.
## PHP
```php
<?php
    $input = array(1, 2, 3, 4, 5, 6);

    $filter_even = function($item) {
        return ($item % 2) == 0;
    };

    // Built-in array_filter accepts both the data and the function
    $output = array_filter($input, $filter_even);
    
    print_r($output);
?>
```
#### Code Explanation:
The output will be: [2,4,6]

PHP supports functional programming. In the above code, we see that the variable $filter_even is a first-class function. It is invoked by the built in function array_filter which accepts an input and a function that limits the input. Here, the function checks if each value in the input is even. No state has been altered in this segment of code.

### Does the language support functional programming?
Yes.