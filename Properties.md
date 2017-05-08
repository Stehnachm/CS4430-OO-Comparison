# Properties

## Swift
```swift
struct Point {
    var x = 0.0, y = 0.0
}
struct Size {
    var width = 0.0, height = 0.0
}
struct Rect {
    var origin = Point()
    var size = Size()
    var center: Point {
        get {
            let centerX = origin.x + (size.width / 2)
            let centerY = origin.y + (size.height / 2)
            return Point(x: centerX, y: centerY)
        }
        set(newCenter) {
            origin.x = newCenter.x - (size.width / 2)
            origin.y = newCenter.y - (size.height / 2)
        }
    }
}
var square = Rect(origin: Point(x: 0.0, y: 0.0),
                  size: Size(width: 10.0, height: 10.0))
let initialSquareCenter = square.center
square.center = Point(x: 15.0, y: 15.0)
print("square.origin is now at (\(square.origin.x), \(square.origin.y))")
// Prints "square.origin is now at (10.0, 10.0)"
```
#### Code Explanation:
In the Rect struct, getters and setters can be seen, they are both also using computer properties to either set information or get it back. A backing variable of called origin is used.
### Getters and setters...write your own or built in?
Getters and setters are not automatically generated but can be created for computer properties.

### Backing variables?
Backing variables 
### Computed properties?
Computed properties are supported natively by Swift.

## PHP
```php
class Post{
    private $properties = ["reply_count" => 25, "number_of_users" => 5];
    
    public function __get($name){
        if ($name === "replyCount"){
            return $this->properties["reply_count"];
        }else if($name === "averagePostsPerUser"){
            return $this->properties["reply_count"]/$this->properties["number_of_users"];
        }
    }
    
    public function __set($name, $value){
        if ($name === "title"){
            $this->properties["title"] = $value;
        }
    }
    
}

$post = new Post();
echo $post->replyCount;
echo $post->averagePostsPerUser;
$post->title = "Hello World";
```
#### Code Explanation:
This code demonstrates how one might replicate properties in PHP.
In the post class, I have set up an array which will hold all of the
class data. I then set up the __get function to return specific properties
from the array based upon the property the user is trying to access. In the
__set method, I demonstrate how to do the same thing with setting a
property. Lastly, I demonstrate how one might use this post class.

### Getters and setters...write your own or built in?
PHP does not automatically create getters or setters, 
those are user defined. It does have a special __get and __set 
functions that are called whenever a property is accessed that would
normally be inaccessible.

### Backing variables?
Backing variables do not exist natively in PHP.

### Computed properties?
Computed properties do not exist natively in PHP however, 
they can be simulated with frameworks or user created code workarounds.