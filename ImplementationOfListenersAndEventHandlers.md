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
<?php

    class Event {

        private static $events = [];

        public static function listen($name, $callback) {
            self::$events[$name][] = $callback;
        }

        public static function trigger($name) {
            foreach (self::$events[$name] as $event => $callback) {
                call_user_func($callback);
            }
        }

    }

    class User {

        public function login() {
            return true;
        }

        public function logout() {
            return true;
        }

    }

    Event::listen('login', function(){
        echo 'User has been logged in!';
    });

    $user = new User();
    $user->login();

    if($user->login()) {
        Event::trigger('login');
    }
?>
```
#### Code Explanation:
This code is a basic login/logout listener. The Event class has a static array of events, as well as a static listen function, which accepts a name of the listened to property, as well as a lambda that will run once that event takes place. The static trigger function will call all of the anonymous functions when the event is triggered. 

The listen method is set with the name login, and a lambda that will echo "User has been logged in!". The output of the script would be that echoed phrase.