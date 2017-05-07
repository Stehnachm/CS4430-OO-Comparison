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
Output: "Hello Dale, Shawn"

In Swift, Events provide a generic mechanism for raising notifications that can be handled by multiple observers. The Event class has a generic parameter T which defines the type of data that this event conveys and the EventHandler typealias declares a function that accepts this type. The rest of this class is pretty straightforward, handlers are added to an array, with each being invoked when the event is raised. In the code, after the declaration of the Event Class, we create an event and add a handler to the eventHandler list. We then can pass multiple parameters to event handlers via tuples.
## PHP
```php
```
#### Code Explanation: