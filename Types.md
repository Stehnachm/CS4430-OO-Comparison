# Types

## Swift
```swift
let string:String = "string"
let int:Int = 1
let bool:Bool = true

let class1 = Class1()

// Value type example
struct S { var data: Int = -1 }
var a = S()
var b = a						// a is copied to b
a.data = 42						// Changes a, not b
print("\(a.data), \(b.data)")	// prints "42, -1"

// Reference type example
class C { var data: Int = -1 }
var x = C()
var y = x						// x is copied to y
x.data = 42						// changes the instance referred to by x (and y)
print("\(x.data), \(y.data)")	// prints "42, 42"
```
#### Code Explanation:
At the top basic types are being created such as String, Int and Bool. Below is a class instantiation, the word "new" is not needed in Swift, instantiation is instead achieved by using parenthesis behind the class name. Last are examples of a reference type and a value type and how data is handled with each of them when reassigning variables. 

### What types does the language support?
Swift supports standard types such as string, cool, double, int, float, character. It also includes an optional type and specific types that are prefixed with “NS”, these are back from the days or Steve Jobs Next Step company that was folded into apple. In Swift 3 more of the types had the “NS” removed in the great renaming.

### Are both reference and value types supported?
Yes, both reference and value types are supported.
### Can new value types be created?
Yes, Swift does support the creation of value types.
## PHP
```php
$string = "Hello world";
$float = 4.53;
$bool = false;

$user = new User();
$post = new Post();

$a = new stdClass(); # <-- Obj1
$a->foo = 'foo';
$b = $a;
$b->foo = 'bar';
echo $b->foo; # outputs 'bar'
echo $a->foo; # outputs 'bar'

$c =& $a;
$c = new stdClass(); # <-- Obj2
$c->foo = 'foo';
echo $b->foo; # outputs 'bar'
echo $a->foo; # outputs 'foo'
```
#### Code Explanation:
The first three lines of code demonstrate some of PHP's value types,
while the next two lines demonstrate a couple of imaginary reference types.
The third block demonstrates one part of PHP's reference system. Because $b
holds a copy of the reference to $a any property changes to $b will also
affect $a. The last block of code demonstrates using a true reference
copy in PHP by using the =& operator. By doing this, any changes to the
value of $c or properties on $c will replicate to $a.

### What types does the language support?
PHP supports the following type: boolean, integer, float, string, 
array, object, callable, iterable, resource, NULL.

### Are both reference and value types supported?
Yes, both reference and value types are supported. All things not 
instantiated as a class are value types. These include boolean, 
integer, float, and string. PHP uses the C style method for copying 
references with the & operator.

### Can new value types be created?
No, PHP does not support the creation of value types.