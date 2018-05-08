# CS4330 Final Project
An object oriented comparison of Python and Java

Alex Gompper, Darrell Martin, Zach Pierucci

# Java

### Language purpose / genesis

1) **Why was the language created?**
   * Java was created to use as few dependencies as possible while being a language built to be used across all platforms. Java Virtual Machine is a large part of what allows it to be used across platforms.
2) **What problems was the language trying to address?**
   * Memory management was the main issue that was trying to be addressed by Java. A garbage collection system was implemented to help with this problem. Java also helps simplify some of the complexity of other languages with its use of different libraries and built in functions.
3) **Is the language a reaction to a previous language or a replacement for another language?**
   * Java was a reaction to the previous dominant language of C++. It tried to fix some of the problems associated with C++, but while still using the OO concepts.

### Unique features of the language

1) **Does the language have any particularly unique features?**
   * One of the unique features of Java is the Java Virtual Machine.  It also is very flexible and can be ran on multiple platforms.

### Name spaces

1) **How are name spaces implemented?**
   * Defining a package: 
```java
package final;
```
   * You can also import other packages and that would look like: 
```java
import java.io;
```
2) **How are name spaces used?**
   * They help group related classes by defining a namespace.  This helps to avoid naming conflicts and keep things organized. Packages are defined at the top of the page and will define which package the class belongs to.

### Types

1) **What types does the language support?**
  * Java supports 8 primitive types. int, double, float, long, short, boolean, byte, and char.
2) **Are both reference and value types supported?**
  * Java supports reference types and has the ability to pass by value and pass by reference.
3) **Can new value types be created?**
  * Java has the ability to create new object types.

### Classes

1) **Defining**
  * Classes have state and behavior in the form of instance variables and methods.
2) **Creating new instances**
  * Instances of objects are created using the “new” keyword and a call to the constructor.
3) **Constructing / initializing**
  * Every class has a constructor even if you do not explicitly write a constructor. There is always a default constructor that takes no arguments, but if you explicitly define a no-arg constructor, the default constructor disappears.
4) **Destructing / de-initializing**
  * Java has a garbage collector that automatically destroys an object when there are no longer any references to it.

### Instance reference name in data type (class)

1) **This? Self?**
  * Java uses ```this```. Within an instance method or a constructor, ```this``` is a reference to the current object, the object whose method or constructor is being called.  You can refer to any member of the current object from within an instance method or a constructor by using ```this```
  
  ```java
	public Obj(int x, int y) {
        		this.x = x;
        		this.y = y;
    	}
  ```
  
### Properties

1) **Getters and setters…write your own or built in?**
  * Getters and setters are not built in, they have to be written, but they are very simple.
  
  ```java
    public int getHeight() {
    		return this.height;
	}

	public void setHeight(int height) {
    		this.height = height;
	}
  ```
2) **Backing variables?**
3) **Computed properties?**

### Interfaces / protocols

1) **What does the language support?**
2) **What abilities does it have?**
3) **How is it used?**

### Inheritance / extension
### Reflection

1) **What reflection abilities are supported?**
2) **How is reflection used?**

### Memory management

1) **How is it handled?**
2) **How does it work?**
3) **Garbage collection?**
4) **Automatic reference counting?**

### Comparisons of references and values

1) **How are values compared? (i.e. comparing two strings)**

### Null / nil references

1) **Which does the language use? (null/nil/etc)**
2) **Does the language have features for handling null/nil references?**

### Errors and exception handling
### Lambda expressions, closures, or functions as types
### Implementation of listeners and event handlers
### Singleton

1) **How is a singleton implemented?**
2) **Can it be made thread-safe?**
3) **Can the singleton instance be lazily instantiated?**

### Procedural programming

1) **Does the language support procedural programming?**

### Functional programming

1) **Does the language support functional programming?**

### Multithreading

1) **Threads or thread-like abilities**
2) **How is multitasking accomplished?**

---

# Python

### Language purpose / genesis

1) **Why was the language created?**
    * The original creator of Python, Guido van Rossum was using the ABC language to do systems administration on Amoeba operating system. Van Rossum also wanted a better way to extend ABC, to help with his complaints.
    * The language was spontaneously named after Monty Python.
2) **What problems was the language trying to address?**
    * Python was designed to be more extenisble than ABC.
3) **Is the language a reaction to a previous language or a replacement for another language?**
    * Python was designed as a successor to the ABC language, sharing the same syntactical style as before.

### Unique features of the language

1) **Does the language have any particularly unique features?**
    * Python has built in functionality for multiple assignement, meaning an iterable object can be automatically unpacked into multiple variables.
    * Python includes a command line interpreter.

### Name spaces

1) **How are name spaces implemented?**
    * Variable declarations automatically take the innermost scope. Once this scope is searched, Python then checks global variables, and then finally the outermost scope containing built in names.
```python
foo = "What's up, world?!"
def my_func():
    foo = "Hello World!"
my_func()
print(foo)  # Output: "What's up, world?!"
```
2) **How are name spaces used?**
    * Python's name spaces are used to give the language it's class structure, as well as lay foundation for the module based extension system.

### Types

1) **What types does the language support?**
    * Python has over 30 different built in types, however a good amount are generally for internal use.
```python
None, int, long, float, complex, bool, str, unicode, basestring, list, tuple, xrange, dict, set, frozenset, type, object, object, file
```
2) **Are both reference and value types supported?**
    * Only reference types are supported in Python. 
3) **Can new value types be created?**
    * New types can be created in Python by writing the typedef in C. However the same functionality can usually be achieved by defining a new class.
    * Once instantiated, these attributes can be accessed directly.
```python
class Particle:
    def __init__(self, mass, position, velocity, force):
        self.mass = mass
        self.position = position
        self.velocity = velocity
        self.force = force
```

### Classes

1) **Defining**
    * Class definitions require at least a `__init__` method with the basic object attributes. This is the classe's constructor.
```python
class Color:
    def __init__(self, red, green, blue, transparency):
        self.red = red
        self.green = green
        self.blue = blue
        self.transparency = transparency
```
2) **Creating new instances**
    * New instances can be created by calling the class constructor
3) **Constructing / initializing**
```python
c = Color(40, 20, 100, 1)
```
4) **Destructing / de-initializing**
    * Python uses the `del` keyword to destroy instances.
```python
del c
```

### Instance reference name in data type (class)

1) **This? Self?**
    * Python uses `self` to reference instance variables within a class.
```python
class Foo:
    def __init__(self, message):
        self.message = message
    def report_message():
        print(self.message)
            
f = Foo("hello world")
f.report_message()  # output: "hello world"
```

### Properties

1) **Getters and setters...write your own or built in?**
    * Generally it is not necessary to write specific getter and setter functions for Python objects. Instead, object attributes can be accessed with dot notation.
```python
class Foo:
    def __init__(self):
        self.bar = "Hello World!"
        
f = Foo()
print(f.bar)  # Output: Hello World!
```
2) **Backing variables?**
    * Backing variables can exist to an extent within a class by using method decorators. 
```python
class Obj:

    ...

    @property
    def attribute(self): 
        return self._attribute

    @attribute.setter
    def attribute_setter(self, value):
        self._attribute = value
```
3) **Computed properties?**
    * Computed properties are easy to implement in a class. 
```python
class Particle:
    def __init__(self, mass, position, velocity, force):
        self.mass = mass
        self.position = position
        self.velocity = velocity
        self.force = mass * velocity
```

### Interfaces / protocols

1) **What does the language support?**
    * Python has interface support in the form of abstract base classes, which were introduced after v2.6.
2) **What abilities does it have?**
3) **How is it used?**
    * Abstract base classes can be used in Python when you don't want to instantiate the parent class, but still provide important functionality to subsequent child classes.

### Inheritance / extension
   * Python has support for multiple inheritance.
```python
class LineCook(Employee, Person):
    ...
    
    # With multiple inheritance, LineCook > Employee > Person
```
### Reflection

1) **What reflection abilities are supported?**
2) **How is reflection used?**

### Memory management

1) **How is it handled?**
    * Python automates the handling of memory allocation for object instances. The memory manager uses a private heap and manages memory dynamically.
2) **How does it work?**
    * At the lowest level, a raw memory allocator ensures that there is enough room in the private heap for storing all Python-related data by interacting with the memory manager of the operating system. 
    * On top of this, other allocators provide memory for object-level instances.
3) **Garbage collection?**
    * The memory manager automates garbage collection automatically. 
4) **Automatic reference counting?**
    * Python has support for automatic reference counting. 

### Comparisons of references and values

1) **How are values compared? (i.e. comparing two strings)**

### Null / nil references

1) **Which does the language use? (null/nil/etc)**
   * Python uses `None`. This is not a reference to 'nowhere' like in C. Instead it is an instance of a `NoneType` object.
2) **Does the language have features for handling null/nil references?**
   * Because the `None` reference is actually an object, it can be compared like any other type. Likewise, incompatible type exceptions are thrown when trying to incorrectly assign or compare a `None` reference.

### Errors and exception handling

* Python uses a `try` and `except` block to catch exceptions as they are thrown by operations inside the block.

```python
try:
    a = "not a number"
    b = int(a)
except ValueError:
    print("Hey I don't think that was a number!")
```
   
### Lambda expressions, closures, or functions as types
   * Lambda expressions are easy to implement in Python.
```python
g = lambda x: x**2

g(3)  # Output: 9
```

### Implementation of listeners and event handlers

    * Python has limited support for event handling. One of the more popular methodologies is to subscribe to a methods event.
    * There are other third party libraries for event listeners such as [PyNotify](https://pypi.org/project/py-notify/).
```python
class MyBroadcaster()
    def __init__():
        self.onChange = EventHook()

b = MyBroadcaster()

b.onChange += myFunction

b.onChange.fire()
```

### Singleton

1) **How is a singleton implemented?**
2) **Can it be made thread-safe?**
3) **Can the singleton instance be lazily instantiated?**

### Procedural programming

1) **Does the language support procedural programming?**

* Python is very procedural. Python is always executed top-to-bottom by the interpreter.
```python
a = 0
print(a)
a += 1
print(a)
a += 1
print(a)

# Output:
# 0
# 1
# 2
```

### Functional programming

1) **Does the language support functional programming?**

* Python supports functional programming.
```python
def step_one(foo):
    return foo * 2
    
def step_two(foo):
    return foo + 3
    
print(step_two(step_one(2)))  # Output: 7
```

### Multithreading

1) **Threads or thread-like abilities**
    * Threading in Python is performed using the Threading module and subclassing the thread object.
2) **How is multitasking accomplished?**

```python
import Threading


class Worker(Threading.thread):
    def __init__(self, id):
        Threading.thread.__init__(self)
        self.foo = 0
        self.id = id
    
    def run():
        for i in range(99999):
            print("[{}] :: {}".format(self.id, self.foo))
            self.foo += 1
            

workers = []           
for i in range(10):
    workers.append(Worker(i))
    workers[i].daemon = True
    workers[i].start()
```
