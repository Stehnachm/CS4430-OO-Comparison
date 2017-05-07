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
#### Errors
The default error handling in PHP is very simple. An error message with filename, line number and a message describing the error is sent to the browser.

One of the easiest methods of error handling is the "die" function, which will stop the execution of the code and display an error message. This is shown below:
```php
<?php
    if(!file_exists("welcome.txt")) {
      die("File not found");
    } else {
      $file=fopen("welcome.txt","r");
    }
?>
```
When stopping the execution of the script is not the right choice, the user can create a function to be called when an error occurs. The user defined function must accept two parameters (error level and error message), but can accept up to five optional parameters. The functions's syntax is:

error_function_name(error_level,error_message, error_file,error_line,error_context)

After the function is created, it must be set. A basic error handler is shown below that is triggered by an undefined variable being called.

```php
<?php
    //error handler function
    function customError($errno, $errstr) {
      echo "<b>Error:</b> [$errno] $errstr";
    }

    //set error handler
    set_error_handler("customError");

    //trigger error
    echo($test);
?>
```
The output of the code would be: 

Error: [8] Undefined variable: test
#### Exceptions
Exception handling in PHP is done primarily by using try, catch, and finally blocks. The code attempts to execute in the try, catches any thrown exceptions in the catch blocks, and always executes the finally block. Multiple catch blocks can be used, and try blocks can be nested. Users are allowed to create their own custom exceptions as well.

```php
<?php
    class customException extends Exception {
      public function errorMessage() {
        //error message
        $errorMsg = 'Error on line '.$this->getLine().' in '.$this->getFile()
        .': <b>'.$this->getMessage().'</b> is not a valid E-Mail address';
        return $errorMsg;
      }
    }

    $email = "someone@example.com";

    try {
      //check if
      if(filter_var($email, FILTER_VALIDATE_EMAIL) === FALSE) {
        //throw exception if email is not valid
        throw new customException($email);
      }
      //check for "example" in mail address
      if(strpos($email, "example") !== FALSE) {
        throw new Exception("$email is an example e-mail");
      }
    }

    catch (customException $e) {
      echo $e->errorMessage();
    }

    catch(Exception $e) {
      echo $e->getMessage();
    }
    
    finally {
      echo "This will always display";
    }
?>
```
#### Code Explanation:
In the above code, the user creates a custom exception handler and defines an errorMessage function. The user then checks first if the email is valid, throwing the custom exception if it is not, then checks if the email contains "example", throwing the default exception if it does. After everything else, the finally block will display its text.