# Implementation of listeners and event handlers

## Swift
```swift
class Event<T> {
    
    typealias EventHandler = (T) -> ()
    
    private var eventHandlers = [EventHandler]()
    
    func addHandler(handler: @escaping EventHandler) {
        eventHandlers.append(handler)
    }
    
    func raise(data: T) {
        for handler in eventHandlers {
            handler(data)
        }
    }
}

let event = Event<(String, String)>()
event.addHandler { a, b in print("Hello \(a), \(b)") }
let data = ("Dale", "Shawn")
event.raise(data: data)
```
#### Code Explanation:
## PHP
```php
```
#### Code Explanation: