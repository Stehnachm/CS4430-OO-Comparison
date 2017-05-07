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
```php

```
#### Code Explanation:

### How is it handled?
### How does it work?
### Garbage collection?
### Automatic reference counting?