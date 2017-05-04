# Refelction

## Swift
```swift
```
#### Code Explanation:

### What reflection abilities are supported?
### How is reflection used?

## PHP
```php
class HelloWorld {
    public $name = "George";

    public function sayHelloTo($name) {
        return 'Hello ' . $name;
    }

}
$hello = new HelloWorld();
$class = new ReflectionClass('HelloWorld');
$methods = $class->getMethods();
$reflectionMethod = $methods[0];
echo $reflectionMethod->invoke($hello, 'Mike');
$prop = $class->getProperty("name");
echo $prop->getValue($hello);
$prop->setValue($hello, "Bob");
```
#### Code Explanation:
In the above code example, a simple class called HelloWorld is created
that has one property and one method. After creating the class, we construct
a reflection class, referencing the class by name. We then extract all
of its methods by using the getMethods method. This will return an array
of ReflectionMethod objects. Among other things, the ReflectionMethod includes
a method called invoke that allows us to execute the given function. To
execute the function, we must supply the instance to operate on and a list
of arguments as shown above. 

Lastly, we demonstrate the ability to get
properties and read / write to them. The third line from the bottom
demonstrates using the getProperty method which returns a ReflectionProperty.
From the ReflectionProperty we can get and set the value of the property
provided we give it an instance to operate on.

### What reflection abilities are supported?
PHP supports full read-write reflection, allowing the user to obtain 
all information about a class through the ReflectionClass. From there, 
you can get methods, the constructor, properties, etc. Additionally 
protected/private members can be seen, but their values cannot be accessed 
through reflection.

### How is reflection used?
To gather information about a class, you construct a ReflectionClass 
passing in either a concrete copy of the class or the class name. 
From there you can use the various methods to extract the information 
about the class that you want. This will be illustrated in the code 
example.
