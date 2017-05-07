# Multithreading

## Swift
```swift
let queue = OperationQueue()

queue.addOperation() {
    // do something in the background
    
    OperationQueue.main.addOperation() {
        // when done, update your UI and/or model on the main queue
    }
}
```
#### Code Explanation:
The code above declares a new OperationQueue and adds an operation to that queue. AddOperation takes has a closure for the operation code to preform when it is executed. Also within the queue.addOperation closure there is a OperationQueue.main.addOperation() which takes a closure that runs on the main thread in order to update the UI.

### Threads or thread-like abilities
Swift supports threads.

### How is multitasking accomplished?
Swift uses Grand Central Dispatch, also known as GCD is a way to optimize performance for processor with multiple cores and also using multi-threading which in a nutshell allows you to run tasks in parallel. iOS Apps are made up of one or more threads. A single core processor and multi-core processor can run multiple threads, just in different manners. Concurrency has to share the resource between the two queues (Single core processor), While parallel queues are split between two resources (Multi core processor). By utilizing GCD we can accomplish multithreading in out applications. Managing these queues allows us to accpmlish tasks in either a synchronous or asynchronous manner.

## PHP
```php
```
#### Code Explanation:

### Threads or thread-like abilities
### How is multitasking accomplished?