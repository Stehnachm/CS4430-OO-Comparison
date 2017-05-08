# Inheritance / Extension

## Swift
```swift
extension Double {
    var km: Double { return self * 1_000.0 }
    var m: Double { return self }
    var cm: Double { return self / 100.0 }
    var mm: Double { return self / 1_000.0 }
    var ft: Double { return self / 3.28084 }
}
let oneInch = 25.4.mm
print("One inch is \(oneInch) meters")
// Prints "One inch is 0.0254 meters"
let threeFeet = 3.ft
print("Three feet is \(threeFeet) meters")
// Prints "Three feet is 0.914399970739201 meters"
```
#### Code Explanation:
This is code block is an extension on the Double class, where you can call its methods on variables of type Double. For example, declaring the var oneInch as 25.4.mm will convert the number to 0.0254 meters since the extension is using computer properties.

#### Explanation:
An extension can be defined similarly to a class by using the keyword extension, this can be then used to add additional functionality to a class. An extension can also extend an existing type and make it adopt protocols.
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
