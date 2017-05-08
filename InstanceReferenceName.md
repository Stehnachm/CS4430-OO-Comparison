# Instance reference name in data type (class)

## Swift
```swift
class ExampleClass{
    var exampleVariable:Int?
    
    init(number:Int){
        print("Hello World")
        self.exampleVariable = number
    }
}

```
#### Code Explanation:
In the class, the initializer takes in an Int and using self will set that to the variable on the class named exampleVariable. 

### this? self?
Swift uses self to reference current scope.
## PHP
```php
class Post {
    protected $title;

    public function __construct($title){
        $this->title = $title;
    }
}
```
#### Code Explanation:
This code demonstrates how to use $this to access properties in
the current scope.

### this? self?
PHP uses $this to reference the current scope.