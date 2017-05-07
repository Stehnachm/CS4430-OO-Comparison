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
```php
```
#### Code Explanation:

### How is a singleton implemented?
### Can it be made thread-safe?
### Can the singleton instance be lazily instantiated?
