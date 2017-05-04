# Types

## Swift
```swift
```
#### Code Explanation:

### What types does the language support?
### Are both reference and value types supported?
### Can new value types be created?

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