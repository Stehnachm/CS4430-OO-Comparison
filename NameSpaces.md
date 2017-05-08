# NameSpaces

## Swift
```swift

import LibraryA

//in LibraryA a function called "example" exists that takes number and doubles it
var two = example(1)

//This is the same as doing...
var four = LibraryA.example(2)
```
#### Code Explanation:
In this code block, LibraryA is being imported. With this all of its methods are being imported into the class. Because of this in the code, methods can be directly called without prefixing the library name. In the example, the method "example" is being called in two different ways, with and without the library name prefix. Both ways will call the function correctly.
#### How are name spaces implemented?
Namespacing in Swift is implicit , so classes are scoped by the modules that they are in, this way you don't need prefixing.
#### How are name spaces used?
After importing a class you will have access to all its methods, for example you import ClassA with a method called doSomething(), you can simply call doSomething() and swift will think you are calling ClassA.doSomething().

## PHP
```php
namesapce App;

use App\User;

class Post {
    protected $user;
    
    public function __construct(User $user){
        $this->user = $user;
    }
}
```
#### Code Explanation:
The above code snippet demonstrates both how to create a namespace, and
how to use a namespaced class. The first line of the file, sets the
namespace to be App. By PSR4, this file should be located in the app 
directory. The next line down imports the User class from the App
namespace using its fully qualified name. The remainder of the code
demonstrates how you can then use this imported class.

#### How are name spaces implemented?
Namespaces are defined at the top of each file using the namespace directive. 
PSR4 recommends that namespaces correspond to the directory hierarchy the class is contained within.

#### How are name spaces used?
To use a function or class from a namespace, you place the use statement 
at the stop, referencing the full qualified name of the class if its a 
class. In the case of functions, you only need to specify down to the 
last namespace name used.