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
Although vanilla PHP does not support multithreading, the PHP documentation recommends using the pthreads API that allows multithreading to be possible. Usage of the API is shown below.
```php
<?php
    class AsyncOperation extends Thread {

        public function __construct($arg) {
            $this->arg = $arg;
        }

        public function run() {
            if ($this->arg) {
                $sleep = mt_rand(1, 10);
                printf('%s: %s  -start -sleeps %d' . "\n", date("g:i:sa"), $this->arg, $sleep);
                sleep($sleep);
                printf('%s: %s  -finish' . "\n", date("g:i:sa"), $this->arg);
            }
        }
    }

    // Create a array
    $stack = array();

    //Initiate Multiple Thread
    foreach ( range("A", "D") as $i ) {
        $stack[] = new AsyncOperation($i);
    }

    // Start The Threads
    foreach ( $stack as $t ) {
        $t->start();
    }

?>
```
#### Code Explanation:
In the above code, the class AsyncOperation extends thread, and defines a run method for the thread. the run method with choose a random amount of time for which the code will sleep, then execution will stop after it has slept. A stack of instances of the thread are created with names "A" through "D", and are all started one after another. Here is a sample of the output, demonstrating that each of the instances run simultaneously. 

Sample output: 
```
12:00:06pm:     A  -start -sleeps 5
12:00:06pm:     B  -start -sleeps 3
12:00:06pm:     C  -start -sleeps 10
12:00:06pm:     D  -start -sleeps 2
12:00:08pm:     D  -finish
12:00:09pm:     B  -finish
12:00:11pm:     A  -finish
12:00:16pm:     C  -finish
```
### Threads or thread-like abilities
PHP supports threads.
### How is multitasking accomplished?
To effectively multitask in PHP, the pthreads API must be used. Using the API is simple, as it does not require the user to do anything apart from start multiple threads. 