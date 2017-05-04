# Classes

## Swift
```swift
```
#### Code Explanation:

### Defining
### Creating new instances
### Constructing/initializing
### Destructing/de-initializing

## PHP
```php
namespace App;

class Post{
    public function __construct($options = null){
        echo "The post is being constructed.";
        if ($options !== null){
            echo "Options were passed in."
        }
    }
    
    public function __destruct(){
        echo "The post is being destroyed.";
    }
    
    public static function withTitle($title){
        $options = array();
        $options["title"] = $title;
        return new Post($options);
    }
    
}

$post = new Post();
$postWithTitle = new Post::withTitle("Hello world");
```
#### Code Explanation:
The above code snippet demonstrates how to construct a class that will
print out something when it is constructed and when it is destroyed.
It also demonstrates how you static methods are used to get around the
limitation of only having one constructor per class. The last two lines
of the code show how to create a new instance through the constructor as
well as the static method.

### Defining
PHP classes are defined with the class keyword.

### Creating new instances
New instances can be created with the new keyword. 
A common practice in PHP is also to use static methods as 
convenience initializers since PHP doesn’t support multiple constructors.

### Constructing/initializing
All construction work happens in the __construct function 
that acts as a constructor for the object.

### Destructing/de-initializing
PHP objects have a __destruct function that is called when 
the object’s ref count reaches zero or during the shutdown procedure.