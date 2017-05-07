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
There are two comparison types in PHP: those that consider whether the values of the variables are the same, and those that consider whether the variables are identical. Operators of the first type are ‘==’, ‘<’, ‘>=’ etc., while the second type includes ‘===’ or ‘!==’. 

If only the values are compared, then PHP will perform some type juggling. If the identicality is being considered, PHP will require that both the type and value of the variables to be the same. 

The following code example shows how the conversion will take place, as well as the difference between comparing values and identicality.
```
<?php

    //equal values
    var_dump(0 == 0); // -> true
    var_dump(1 >= 0); // -> true
    var_dump("dale" == "dale"); // -> true
    var_dump("dale" != "shawn"); // -> true
    
    
    //identical
    var_dump(0 === 0); // -> true
    var_dump(0 === "0"); // -> false
    
    //converting to compare values
    var_dump(0 == "a"); // 0 == 0 -> true
    var_dump("1" == "01"); // 1 == 1 -> true
    var_dump("10" == "1e1"); // 10 == 10 -> true
    var_dump(100 == "1e2"); // 100 == 100 -> true
    
    //instances with identical members
    $a = new stdClass();
    $a->foo = "bar";
    $b = clone $a;
    var_dump($a === $b); // -> false

?>
```
#### Code Explanation:
The first two blocks illustrate the difference between value and identicality comparison. The next section shows how the types are converted to check if the values are the same. The final section elicits that instances with the same members cannot be compared with the indenticality operator.
