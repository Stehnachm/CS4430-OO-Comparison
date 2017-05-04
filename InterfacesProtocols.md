# Interfaces / Protocols

## Swift
```swift
```
#### Code Explanation:

### What does the language support?
### What abilities does it have?
### How is it used?

## PHP
```php
interface iTemplate{
    public function setVariable($name, $var);
    public function getHtml($template);
}

trait ComputesProperties{
    public $numberOfTimesUsed = 10;
    
    public function incrementTimesUsed(){
        $this->numberOfTimesUsed++;
    }
}

class Template implements iTemplate{
    use ComputesProperties;
    
    private $vars = array();
      
        public function setVariable($name, $var)
        {
            $this->vars[$name] = $var;
        }
      
        public function getHtml($template)
        {
            foreach($this->vars as $name => $value) {
                $template = str_replace('{' . $name . '}', $value, $template);
            }
     
            return $template;
        }
}

$template = new Template();
echo $numberOfTimesUsed;
$template->incrementTimesUsed();
```
#### Code Explanation:
The above code snippet demonstrates how to define an interface and
trait in PHP. It then shows how to construct a class that implements
the interface and uses the trait. Lastly, at the end of the snippet, the
use of the trait property and method are demonstrated. Even though they
are never explicitly defined in the class, they are still available to us
since we used the trait.

### What does the language support?
PHP supports interfaces and traits. 
Interfaces work similarly as interfaces in other languages. 
Traits allow the user to include fully completed code blocks without 
having to extend from a specific class or implement an interface.

### What abilities does it have?
PHP interfaces can define method signatures and constants. 
They cannot define normal properties. Traits can define concrete 
methods and variables which become available to the class when it uses it.

### How is it used?
Interfaces are defined in separate files using the interface keyword, 
following the PSR4 naming scheme. Traits are defined the same way,
but with the trait keyword instead of the interface keyword.