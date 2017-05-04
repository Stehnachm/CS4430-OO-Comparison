# Inheritance / Extension

## Swift
```swift
```
#### Code Explanation:

#### Explanation:

## PHP
```php
abstract class AbstractBase{
    abstract public class sayHello();
}


class Base extends AbstractBase {
    public function sayHello() {
        echo 'Hello';
    }
}

trait ComputesProperties{
    public $timesToSayHello = 5;
    
    public function sayHelloTimes(){
        for($i = 0; $i < $timesToSayHello; $i++){
            echo "Hello";
        }
    }
}

class Concrete extends Base{
    use ComputesProperties;
    
    public function goodbye(){
        echo "Goodbye";
    }
}

$concrete = new Concrete();
$concrete->timesToSayHello = 2;
$concrete->sayHelloTimes();
$concrete->goodbye();
```
#### Code Explanation:
The above code demonstrates extending from an abstract base class and then
extending from that class again to make another concrete class. It also
further demonstrates the use of traits as a way to add functionality
to a class through horizontal composition.

#### Explanation:
PHP does not support extensions. 
It does support the addition of code to a class through traits but this 
should only be done on classes that you define. PHP supports the standard
style of extends and inheritance that is present in most OOP languages.
