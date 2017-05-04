# NameSpaces

## Swift
```swift
```
#### Code Explanation:

#### How are name spaces implemented?
#### How are name spaces used?

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