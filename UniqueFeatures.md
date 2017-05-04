# Unique features of the language

## Swift
```swift
```
#### Code Explanation:

### Does the language have any particularly unique features?

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
