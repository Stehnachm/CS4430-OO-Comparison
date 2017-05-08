# Memory Management

## Swift
```swift
class User {
    var name: String
    
    init(name: String) {
        self.name = name
        print("User \(name) is initialized")
    }
    
    deinit {
        print("User \(name) is being deallocated")
    }
}

do {
    let user1 = User(name: "Dale")
}
```
#### Code Explanation:
When this playground is run we can see when ARC handles the allocation and deallocation of memory for the User object. Print statements fire when allocation of memory happens in the init and when deallocation of memory happens in deinit for demonstration purposes.

### How is it handled?
Swift handles much of the memory management of applications behind the scenes. Swift allocates or deallocates memory on your behalf using a method called Automatic Reference Counting or "ARC". Using ARC allows for developers to be able to reliably predict when memory will be allocated or deallocated based on reference counts.
### How does it work?
Apple Summaries how ARC works by saying: "Swift uses Automatic Reference Counting (ARC) to track and manage your app’s memory usage. In most cases, this means that memory management “just works” in Swift, and you do not need to think about memory management yourself. ARC automatically frees up the memory used by class instances when those instances are no longer needed."

Upon slightly deeper examination, when apple says "when those instances are no longer needed", they actually mean when thier reference count is 0.
### Garbage collection?
Swift uses ARC as opposed to garbage collection.
### Automatic reference counting?
See above. Swift Uses ARC.

## PHP

### How is it handled?
PHP stores every variable value in a struct called _zval_struct, meaning zend value. This struct contains information about the variable including value, type, type_info, and more. For for information on how each of the members of the zval are stored in memory, reference [this page](https://nikic.github.io/2015/05/05/Internal-value-representation-in-PHP-7-part-1.html) that explores how exactly PHP 7 stores values in memory. The most important pieces of the zval struct for memory management purposes are is_ref, which tells whether or not the variable is a part of a reference set, and refcount, which tells how many variable point to that zval container. A zval container is created when a new variable is created with a constant value.
### How does it work?
PHP automatically creates and allocates the required memory for the user, as well as setting all of the zval information. The user can use some memory management APIs to directly manipulate memory if they desire to do so.
### Garbage collection?
PHP performs garbage collection at three primary junctures: when you tell it to, when you leave a function, and when a script ends. Situation 1 will occur if you use unset() or other resource-destroying functions that explicitly clear up after your variables. The second situation will occur if any variable leaves scope, or is no longer needed. The last situation will occur when a script has finished execution, and it will clean all script related activities for the user.
### Automatic reference counting?
Reference counting is done automatically by PHP as a part of the zend value. The code below demonstrates exactly how it works.
```php
<?php
    $a = "new string";          //new zval container created
    $c = $b = $a;               //refcount increased to 3
    xdebug_debug_zval( 'a' );
    $b = 42;                    //new zval container created, one refcount removed from other container
    xdebug_debug_zval( 'a' );
    unset( $c );                //variable c destroyed, refcount reduced
    xdebug_debug_zval( 'a' );
?>

```
#### Code Explanation:
This code will have the following output:
```
a: (refcount=3, is_ref=0)='new string'
a: (refcount=2, is_ref=0)='new string'
a: (refcount=1, is_ref=0)='new string'
```
Here it is shown how the refcount can increase and decrease based upon the number of variables that reference a specific constant value. It is also shown that the unset() function can be used to destroy a variable. 