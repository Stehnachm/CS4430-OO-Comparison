# Singleton 

## Swift
```swift
class Singleton {
    static let sharedInstance = Singleton()
    private init() {}
    var names : [String] = []
}

Singleton.sharedInstance.names = ["Dale", "Shawn"]

print(Singleton.sharedInstance.names)
```
#### Code Explanation:
Output: ["Dale", "Shawn"]

In swift, A Singleton can be declared in the manner secified above. The singleton pattern is a software design pattern that restricts the instantiation of a class to one object. In the code above we can see a class called Singleton is declared with a static constant called sharedInstance of type Singleton. A private init() is then created which prevents others from using the default '()' initializer for this class. A local variable names of type string array is then declared for illustration purposes. In the lines outside of the class the contents of the Singleton names array is printed.


### How is a singleton implemented?
See Code Explanation section above.
### Can it be made thread-safe?
Swift singleton creation is thread safe. This doesn't guarantee that the functions you call in the singleton instance will be magically thread safe. There are several methods that can be implemented to make the functions that you call within the singlton to be thread safe.
### Can the singleton instance be lazily instantiated?
In our implementation, the singleton cannot use the lazy keyword for instantiation. The singleton can have variables that are lazily instantiated.

## PHP
### How is a singleton implemented?
A singleton can be implemented in PHP by creating a class that can only be instantiated once. This is done by having a static variable that keeps track of whether or not the class has been instantiated, and does not allow instantiation if it has. 
### Can it be made thread-safe?
Yes, it can be made thread by maintaining the status of the instance in a static variable on the class. Any subsequent calls to the creation method will return the already created instance.
### Can the singleton instance be lazily instantiated?
Yes, the singlton can be lazily instantiated by putting the instance creation inside of a static method of the class that can be accessed by the user.
```php
<?php
    class Singleton
    {
        // Hold an instance of the class
        private static $instance;

        // Creation method
        public static function getSingleton()
        {
            if (!isset(self::$instance)) {
                self::$instance = new __CLASS__;
            }
            return self::$instance;
        }

    }
    $singleton1 = User::getSingleton();
    $singleton2 = User::getSingleton();
    
?>
```
#### Code Explanation:
Here, the class "Singleton" contains a static variable which holds the instance, and a static get method which returns the Singleton instance. If one does not already exist, it is created then returned. Both $singleton1 and $singleton2 will be referencing the same variable, as it was created with the first line, and referenced again with the second.