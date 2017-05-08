# Unique features of the language

## Swift
```swift
var variable1:String?
var variable2:Int?

if let exampleVariable:String = variable1{
    //If variable1 is not nil you would be able to access to via exampleVariable here
}

guard let exampleVariable2:Int = variable2 else{
    //If variable2 is nil handle it here
}

 //If variable2 is not nil, its data will not be in exampleVariable2 and you can access it where beeded below the guard

```
#### Code Explanation:
At the top there are 2 variables declared, variable1 and variable2. They are both created as optional and since no data was inserted into them they are both nil. in the first code block, Swift will check to see if variable1 is nil, if it has data it will set exampleVariable1 to that data and enter the block. If variable1 is nil the if let will fail and the error will need to be handled after the code block. Next is the guard statement, this has effectively the same functionality of the if let but scopes it differently. If variable2 is nil, you will enter the code block and can handle the error inside the guard. If the data was not nil you can use it as the variable exampleVariable2 in the rest of the scope.
### Does the language have any particularly unique features?
Optionals are built in from the beginning and are heavily relied upon across the entire language.
## PHP
```php
    $className = "stdClass";
    $fred = new $className;
    
    $className2 = "App\User";
    $sue = new $className2;
    
     $fred->{"fooBar"}();
```
#### Code Explanation:
The first two lines construct an stdClass from the string name of the class. 
The next two lines construct a User object that is in the App namespace. 
Because of this, we must supply the fully qualified name. The last line calls the fooBar method on the stdClass by using its string representation.

### Does the language have any particularly unique features?
Classes can be constructed from string representations of their fully qualified name. 
Methods can be called from a string representation of their name. 
Code can be included with things called Traits.
