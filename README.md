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
  * Java supports 8 primitive types. `int, double, float, long, short, boolean, byte, char`
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
  * Java uses this. Within an instance method or a constructor, this is a reference to the current object, the object whose method or constructor is being called.  You can refer to any member of the current object from within an instance method or a constructor by using this
  
```java
public Obj(int x, int y) {
	this.x = x;
	this.y = y;
}
```
  
### Properties

1) **Getters and setters...write your own or built in?**
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
	* Java does not support backing variables.
3) **Computed properties?**
	* Java does not support computed properties.

### Interfaces / protocols

1) **What does the language support?**
2) **What abilities does it have?**
3) **How is it used?**

### Inheritance / extension
 * Java supports inheritance, but it does not support multiple inheritance.  Classes that don’t inherit from another class will always inherit from Object.

### Reflection

1) **What reflection abilities are supported?**
	* Java allows the inspection of methods, classes, fields, and interfaces at runtime. 
2) **How is reflection used?**
	* Java reflection is performed using the `java.lang.reflect` package.
	* Java reflection is used to gather knowledge on the program without knowing the actual name of the fields beforehand.

### Memory management

1) **How is it handled?**
	* Java objects exist in the heap, which is created and managed by the JVM.
2) **How does it work?**
	* The JVM dynamically allocates and deallocates memory at runtime.
3) **Garbage collection?**
	* Once the heap is filled or once the program has completed, the garbage collector is ran which removes unused objects, thus freeing up more space and preventing overflow issues.
4) **Automatic reference counting?**
	* The garbage collector tracks the number of references to a given object in memory, and then algorithmically decides if the instance is still in use or not.

### Comparisons of references and values

1) **How are values compared? (i.e. comparing two strings)**
	* To properly compare objects in Java, one should use the `equals()` method. This is because the `==` operator will compare the object references, which may not be equal even if their contents are.

### Null / nil references

1) **Which does the language use? (null/nil/etc)**
	* Java uses `null`
2) **Does the language have features for handling null/nil references?**
	* Exceptions are thrown when a null variable is improperly referenced.

### Errors and exception handling
   * Java uses `try` and `catch` blocks to contain exceptions and handle them as they occur.
```java
try
{
     // code that might throw an exception
}
catch (exception(type) e(object))
{
     // logging and/or handing code to prevent the error from crashing the rest of the program
}
```
### Lambda expressions, closures, or functions as types
 * Java doesn’t support closures, but instead uses nested classes which can be either local or anonymous.  Java also uses lambda expressions to define these inner classes.  A lambda expression can be noticed by the ```->```
 
```java
	(parameter-list) -> {	
	// statements
}
```
 

### Implementation of listeners and event handlers
 * Java uses multiple different listeners and event handlers especially for handling different events such as actionEvent and mouseClick.
 
```java
server.addEventListener("message", clientData.class, new DataListener<clientData>() {        
	@Override        
	public void onData(SocketIOClient client, clientData data, AckRequest ackRequest) throws Exception {            System.out.println("Message from client: " + data.getMessage());        
	}    
});
```

### Singleton

1) **How is a singleton implemented?**
 * A singleton is created by making a constructor as private, then writing a static method that has return type object of this singleton class.
2) **Can it be made thread-safe?**
 * Yes they can.
3) **Can the singleton instance be lazily instantiated?**
 * Yes, requiring no memory or resources until needed.

### Procedural programming

1) **Does the language support procedural programming?**
 * No, Java is designed to be completely object oriented and non procedural.

### Functional programming

1) **Does the language support functional programming?**
 * Yes, in Java 8, Lambda expressions were introduced. They are said to be among the biggest features of the Java 8 version. Lambda expression allows functional programming, and makes development simpler in some areas.

### Multithreading

1) **Threads or thread-like abilities**
 * Java supports multi-threaded applications and it is actually multi-threaded by default (i.e. the JVM is one thread and your program is another).

2) **How is multitasking accomplished?**
 * By either Implementing the ```Runnable``` interface

```java
 class MultithreadingDemo implements Runnable
{
    public void run()
    {
        try
        {
            // Displaying the thread that is running
            System.out.println ("Thread " +
                                Thread.currentThread().getId() +
                                " is running");
 
        }
        catch (Exception e)
        {
            // Throwing an exception
            System.out.println ("Exception is caught");
        }
    }
}
```

 * Or by Extending the ```Thread``` class
```java
class MultithreadingDemo extends Thread
{
    public void run()
    {
        try
        {
            // Displaying the thread that is running
            System.out.println ("Thread " +
                  Thread.currentThread().getId() +
                  " is running");
 
        }
        catch (Exception e)
        {
            // Throwing an exception
            System.out.println ("Exception is caught");
        }
    }
}

```

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
    * Python includes an interactive command line interpreter.

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
    * Class definitions require at least a `__init__` method with the basic object attributes. This is the class's constructor.
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
	* Abstract base classes provide some level of functionality while still requiring the remainder of the method to be implemented later on. This functionality is provided with the `ABC` module (Abstract Base Class).
3) **How is it used?**
    * Abstract base classes can be used in Python when you don't want to instantiate the parent class, but still provide important functionality to subsequent child classes.

```python
from abc import ABC, abstractmethod
 
class AbstractClassExample(ABC):
    
    @abstractmethod
    def do_something(self):
        print("Some implementation!")
        
class AnotherSubclass(AbstractClassExample):
    def do_something(self):
        super().do_something()
        print("The enrichment from AnotherSubclass")
        
x = AnotherSubclass()
x.do_something()
```

### Inheritance / extension
   * Python has support for multiple inheritance.
```python
class LineCook(Employee, Person):
    ...
    
    # With multiple inheritance, LineCook > Employee > Person
```
### Reflection

1) **What reflection abilities are supported?**
	* Python provides several functions for reflection
```python
type(), isinstance(), callable(), dir(), getattr()
```
2) **How is reflection used?**
	* Reflection can be used in Python to import dynamically loaded modules
```python
def my_import(name):
    components = name.split('.')
    mod = __import__(components[0])
    for comp in components[1:]:
        mod = getattr(mod, comp)
    return mod
```

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
	* The 'Pythonic' way to compare strings generally uses the `is` operator instead of the `==` operator.
	* In Python, a True return value from an `is` comparison signifies that the two instances being compared are *identical*, whereas the `==` operator signifies the two are *equal*.
```python
a = "alex"
z = "zach"

a is z
# False

a is "alex"
# True

id(a) == id("alex")
# True

id(a) is id("alex")
# False
```

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
	* One pattern for creating a singleton is to use two constructors, ensuring that only one instance is ever available at a time.
```python
class OnlyOne:
    class __OnlyOne:
        def __init__(self, arg):
            self.val = arg
        def __str__(self):
            return repr(self) + self.val
    instance = None
    def __init__(self, arg):
        if not OnlyOne.instance:
            OnlyOne.instance = OnlyOne.__OnlyOne(arg)
        else:
            OnlyOne.instance.val = arg
    def __getattr__(self, name):
        return getattr(self.instance, name)
```
2) **Can it be made thread-safe?**
	* This pattern can be made thread-safe by interrupting the ongoing threads before operating on the singleton. 
	* A better method is to utilize the `Queue` module (thread-safe) to provide a means of exchanging information across threads.
3) **Can the singleton instance be lazily instantiated?**
	* With the above pattern, singleton instances can be lazily instantiated.
```python
x = OnlyOne('dab')
```

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
