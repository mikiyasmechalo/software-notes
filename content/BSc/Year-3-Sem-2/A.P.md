---
title: Advanced Programming
---
# CH 1: Functional Programming
## Programming Paradigms
is a style, or “way,” of programming.
Common Paradigms:
- Rule-Based.
- Structured.
- Procedural.
- Object-Oriented.
- Functional.

Imperative Paradigms  - command driven (not rule based)
- instructions are done in a given order, control flow here is explicit.
- e.g. Procedural, Structural, OOP

Declarative Paradigms -
- focus on the logic of program and the end result
- control flow is not the important, it is the end result that is important
- e.g. Functional and Logic (Rule-based)

**Imperative Programming**: Focuses on how to perform tasks through a series of instructions.
**Object-Oriented Programming (OOP)**: Organizes code into objects that combine data and behavior.
**Functional Programming**: Emphasizes the use of pure functions and immutable data.
**Declarative Programming**: Focuses on what the outcome should be without explicitly listing the steps to achieve it.
- Examples of declarative programming in Java include functional programming, the Stream API, and SQL.

## Functional Programming
Modern java supports two primary programming paradigms ;  Imperative and Declarative
Imperative: procedural , object oriented programming
	e.g. Procedural: c, FORTRAN, OOP  C++,C#, java
Declarative: functional and logic programming
	e.g. Functional: Haskell, ML Logic: prolog
Modern java is a “Hybrid” that combines object-oriented & functional programming
based on the concept of Function / attempts by composing function

Functional Programming treats computation as the evaluation of mathematical functions.
Methods are procedures where we write a sequence of instructions to tell the machine what to do.
In FP, functions are treated like mathematical functions where we map inputs to outputs to produce a result. E.g. `f(x)=3x`.
Functions are isolated and independent, and they depend only on the arguments passed to them and do not alter the program's state like modifying a global variable.

e.g. 
```java
// Imperative
List<String> map(List<String> lines, String omit) {
	List<String> res= new ArrayList<>();
	for(String line : lines)
	if(!omit.equals(line))
		 res.add(line);
	 return res;
}
//functional
List<String> zap(List<String> lines, String omit) { // strea, API
   return lines
	  .stream()  // convert list into a stream
	  .filter(not(omit::equals)) //remove a line in the
			   //stream that matches the “omit” parameter
	  .collect(toList()); // Collect all non-matching lines
			  //into a list & return it to the caller
}
List<String> names = Arrays.asList("John", "Alice", "Bob"); 
names.sort((s1, s2) -> s2.compareTo(s1));
```

Java’s object-oriented programming features make code understandable by encapsulating the moving parts.
It’s functional programming features make code understandable by largely eliminating the moving part.

Lambda expressions
```java
// Traditional way using an anonymous class
Runnable r1 = new Runnable() { //Runnable is just an example class
    @Override
    public void run() {
        System.out.println("Hello, world!");
    }
}
// Using Lambda Expression
Runnable r2 = () -> System.out.println("Hello, world!");
```

key concepts:-
1. Functions as first class citizens
2. Pure functions
	- The execution of the function has no side effects.
	- The return value of the function depends only on the input parameters passed to the function.
	- Treats data as being immutable, & No I/O operations allowed inside.
	- predictable, reusable, and easier to test.
3. Higher order functions
	- The function takes one or more functions as parameters.
	- The function returns another function as result.
4. Functions as first class objects: functions are first class objects in the language → create an instance of a function.
	- Functions can be assigned to a variable and then can be used later.

```java
public class AdvancedProgramming {
	public void lecture(){ /*statement*/ };
	public void labSession(){ /*statement*/ }
	public class void main(String args [ ]){
		AdvancedProgramming ap = new Advancedprogramming();
	}
}
// javacscript FFCO
const advancedProgramming = (parameter1, parameter2) => { /*statement*/ }
```


**Rules/ Protocols** 
- **NO STATE**: no state external to the function
- **NO SIDE EFFECT**: a function cannot change any state outside of the function
- **IMMUTABLE VARIABLES**: Immutable variables makes it easier to avoid side effects.
- **RECURSION OVER LOOPING**: Recursion uses function calls to achieve looping,

It is used to implement concurrency/parallelism because pure functions don’t change variables or any other data outside of it.
It adopts lazy evaluation which avoids repeated evaluation because the value is evaluated and stored only when it is needed.

## Packages
are container that groups related types, such as classes, interfaces, enumerations, and annotations.
Key reasons to use packages:
- To avoids namespace conflict
- To write a better maintainable code

2 Types:
1. Built-in packages - A Library of prewritten classes
2. User-defined Packages - created using `package package_name` at the start of a class.

Syntax for importing a single class - `import package.name.Class` 
Syntax Import the whole package - `import package.name.*` 

Example Built in packages:
`java.util.concurrent` The Java Concurrency Package contains utility classes and interfaces for implementing programs that can perform multiple tasks in parallel.

`java.sql` The JDBC Package contains classes and interfaces for working with databases

`javax.media` The The Java Media Framework Package contains classes and interfaces for working with Java’s multimedia capabilities.


`import static packageName.className.*;` | static import
Allows members ( fields and methods ) defined in a class as public static to be used in Java code without specifying the class in which the field is defined

## The Collections Framework

Data Structures and Algorithms, Recap.
- Representations → List, `ArrayList`, vectors, Queue, Tree, `LinkedList`, etc.
- Operations → Searching, Sorting, Deletion, Inserting, Updating, Manipulating, etc.

**Collections in Java | The Collection Framework** 
The Java Collections Framework (JCF) is a set of classes and interfaces that implement commonly used collection data structures such as lists, sets, maps, and queues. 

Collections refer to a collection of individual objects that are represented as a single unit.
JCF provides an architecture/ standards to store and manipulate a group of objects.

The framework has :
1. interfaces
2. classes
3. algorithms

These Collections are found in the `java.util` package API.

### Benefits of Using Collections

1. **The Iterator Interface**, `java.util.Iterator`
    `Iterator<T> iterator_object = element.iterator();`
    iterates the elements used traverse the list and modify the elements.
    iterator interface has three abstract method:
    - `public boolean hasNext()`
    - `public object next()`
    - `public void remove()`
    - `forEachRemaining()`
    
```java
ArrayList<Integer> arrayElemets = new ArrayList<Integer>();
arrayElemets.add(1);
arrayElemets.add(2);

Iterator<Integer> iterate = arrayElemets.iterator();
while (iterate.hasNext())
	System.out.println(iterate.next());
```


**Collection Interface**
- The root interface of the java collection framework
- `interface Collection<E>`
- not directly implemented but through its sub-interfaces, → List, set and Queue
- **List:** is add and remove elements like an array.
- **Set:** is to store elements in different sets similar to the set in mathematics.
- **Queue:** is interface used to store and access elements in FIFO, LIFO and etc.
    Collection has Methods to Perform actions: `add()`, `size()`, `remove()`, `iterator()`, `addAll()`, `removeAll()`, `clear()`.

In addition to the collection interfaces, collections also use the `Comparator`, `RandomAccess`, `Iterator`, `ListIterator`, and `Spliterator` interfaces.
### List Interface
is collection that allows us to store and access elements sequentially.
**`List`** itself is an abstract class and cannot be instantiated, we use `ArrayList`, `LinkedList`, `Vector` and `Stack` instead.

We have additional methods such as `get()`, `set()`, `toArray()`, `contains()`.

**LinkedList**
non-contagious memory location

Methods
- `boolean add(Object obj)`,
- `void add(int index, Object element)`,
- `void addFirst(Object obj)`,
- `void addLast(Object obj)`,
- `int size()`,
- `int indexOf(Object element)`,
- `int lastIndexOf(Object element)`.

### Queue Interface
Each basic method exists in two forms:
- one throws an exception if the operation fails
- The other returns a special value.

`ArrayDeque`, `LinkedList`, `Priority queue` implements the Queue interface.

Methods:

- `boolean add(Object)`,
- `boolean offer(object)`,
- `Object remove()`, throws `NoSuchElementException` if empty.
- `Object poll()`, - same as `remove()` but returns null if empty rather than throwing exception
- `Object element()` - retrieves the head without removing it
- `Object peek()` - same as element but returns null instead if throwing an exception.

```java
Queue<Integer> lqueue = new LinkedList<>(); // implementing using Linked List
Queue<Integer> pqueue = new PriorityQueue<>(); // implementing using PriorityQueu
```

adding and removing from both sides of a queue is available via the **Deque** interface.

The `ArrayDeque` class provides the implementation of both Queue and Deque.

`addFirst()`, `OfferLast()` , `getFirst()`, `getLast()`, `PeekLast()`, `removeLast()` are included from Deque.

`remove(element)` returns and removes the specified element from the head of the array deque.

### Set Interface
provides the features of the mathematical set.
Sets cannot contain duplicate elements.

`HashSet` {Hash Table DS}, `LinkedHashSet`, `EnumSet`, `TreeSet`{hash tree DS}→ Implements interfaces set.

**Union, Intersection and Subset**

| Methods         | Description                                                                                       |
| --------------- | ------------------------------------------------------------------------------------------------- |
| `iterator()`    | returns an iterator that can be used to access elements of the set sequentially                   |
| `addAll()`      | adds all the elements of the specified collection to the set → Union                              |
| `retainAll()`   | retains all the elements in the set that are also present in another specified set → Intersection |
| `containsAll()` | returns true if the set contains all the elements of the specified collection → Subset            |

**Tree Set**
Navigation methods : `first()` and `last()` element of the set
Methods:
- `lower()`→ Returns the greatest element among those elements that are less than the specified element.
- `higher()`→ returns the lowest element among those elements that are greater than the specified element.
- `floor()`→ returns the greatest element among those elements that are less than the specified element
- `ceiling()`→ returns the lowest element among those elements that are greater than the specified element.

---

**Linked Hash Set**
Provides functionalities of both the **hash table** and the **linked list** data structure.
Implements the `Set` interface while maintaining insertion order. The linked list defines the order in which elements are inserted in hash tables.

contains all the union & intersection Operations from Set. not Subset❔

**Faster than `TreeSet` but Slightly Slower than `HashSet`**


**Exception Handling** - [**Declaring, Throwing, and Catching Exceptions**](https://www.notion.so/Declaring-Throwing-and-Catching-Exceptions-2c4736517e314f1aa6bdf23b8d5460d8?pvs=21) 

## Lambda Expressions/ Anonymous Functions

Its Anonymous Function.
Why Lambda?
- Lambda converts the code segment into an argument
- No need to instantiate a class to create: an object of a functional interface
- Its like an Object

Syntax:
```java
() -> { /*function body*/ }
//e.g.
() -> System.out.println("Lambda Expressions")
Runnable r2 = () -> System.out.println("Hello, world!");
//
List<Integer> list = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
int sum = list.stream().reduce(0, (a, b) -> a + b);
```

### Functional Interface
- aka Single Abstract Method (SAM) interface in java.
- is an interface that only has one abstract method.
- also contain default and static methods which do have an implementation.

Two Kinds:
1. User-defined &
2. Built-in Functional interfaces

Java functional interface can be implemented by a **Lambda Expression**.
Functional interfaces are key for functional programming.
e.g. Built-in functional interfaces
- Runnable → `run()`
- Comparable → `compareTo()`
- `ActionListner` → `actionPerformed()`
- Callable → `call()`

Types of functional interfaces.
1. Function
2. Supplier
3. Consumer
4. Predicate

-  **`Function` Functional Interfaces**    
    receives a single argument, processes it, and returns a value.
```java
import java.util.function.Function; //found in
public interface Function<T, R>{
	R apply(T t);
}
// T is the type of the input argument
// R is the return type of the function
// apply is abstract method

//e.g.
@FunctionalInterface
interface MathOperation {
	int operate(int a, int b);
}
public static void main(String[] args) {
	MathOperation addition = (a, b) -> a + b;
	System.out.println(addition.operate(5, 3));  // Output: 8
}
```
    
-  **`Supplier` Functional Interfaces**
    It represents a function which does not take in any argument but produces a value of type.
```java
import java.util.function.Supplier;
public interface Supplier<T>{
	T get();
}
//e.g.
Supplier<Integer> randomSupplier = () -> new Random().nextInt(100);
System.out.println(randomSupplier.get());
Supplier<String> currentTimeSupplier = () -> LocalTime.now().toString();
```
    
-  **`Consumer` Functional Interfaces**
    a functional interface that accepts an argument and returns no result.
    interface contains two methods
    - `accept()`
    - `andThen()`
    
```java
import java.util.function.Consumer;
public interface Consumer<T>{
	void accept(T t);
}
//e.g.
Consumer<Integer> printNumber = num -> System.out.println("Number: " + num);
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5); 
numbers.forEach(printNumber);
//e.g. how to use: andThen()
Consumer<T> consumer1 = ...;
Consumer<T> consumer2 = ...;
Consumer<T> combinedConsumer = consumer1.andThen(consumer2);
```
    
-  **`Predicate` Functional Interfaces**
    a functional interface takes a single argument and returns a Boolean value.
    
```java
import java.util.function.Predicate;
public interface Predicate<T>{
	boolean test(T t);
}
//e.g.
List<String> names = Arrays.asList("John", "Jane", "Mike", "Jake");
Predicate<String> startsWithJ = name -> name.startsWith("J");
List<String> filteredNames = names.stream()
		.filter(startsWithJ).collect(Collectors.toList());
```

Difference between Predicate and Function
Predicate- we have to pass single argument of any type and Boolean type     
		   value will be returned
		   - we have a method test( ) with predicate
Function – we have to pass parameter type, return type
		  - any parameter can be passed and any value  will be returned
		  - we have apply ( ) method in function
`Function <Integer, Integer>   f1 = n -> n*2;`
`Predicate<Integer> p1 = i -> i%2==0;`

Summary of Functional Interfaces

| Functional Interface | Input   | Output          | Purpose                                      |
| -------------------- | ------- | --------------- | -------------------------------------------- |
| `Function<T, R>`     | Yes (T) | Yes (R)         | Transforms input data                        |
| `Predicate<T>`       | Yes (T) | Yes (`boolean`) | Evaluates a condition                        |
| `Consumer<T>`        | Yes (T) | No              | Performs an action without returning a value |
| `Supplier<T>`        | No      | Yes (T)         | Generates values without input               |
### Functional Composition // not taught in class
a technique to combine multiple functions to a single function which uses the combined functions internally.

Two types
- Predicate Composition
    - `and()`: used to combine two other Predicate functions
    - `or()`: used to combine a predicate instance with another, to compose a third instance.
- Functional Composition
    - `compose()`
    - `andThen()`

Create username checks whether the given username `%a` and `f%`; (Using two Predicates Function)

```java
import java.util.function.Predicate;
public static void main(String[] args) {
	String username = "%auserf%";  // Test username
	Predicate<String> containsA = u -> u.contains("%a");
	Predicate<String> containsF = u -> u.contains("f%");
	Predicate<String> isValidUsername = containsA.and(containsF);
	if (isValidUsername.test(username)) {
		System.out.println("Valid Username!");
	} else { System.out.println("Invalid Username!"); }}
```

## Object Serialization
is the process of converting the Object's state into a Byte Stream.

Byte Stream can be stored, shared, and used by Java machines to reconstruct the objects.
> Object ↔ Byte Code

Object is serializable if f:
- a class or any of its parent classes implement either of the interfaces from java.io

Serializable interface
- defines no members
- it is simply used to indicate that a class may be serialized.
- `writeObject()` method of `ObjectOutputStream` → Serialization
- `readObject()` method of `ObjectOutputStream` → Deserialization

Externalizable sub-interface.
- The programmer may need to have control over these processes.

Serialization
```java
import java.io.Serializable;
public class ClassName implements Serializable {
	// data members
	// member function implmentation
}
// Main function
public class MainClassName {
	public static void main(String[] args) {
		ClassName objectName = new ClassName()
		try{
				FileOutputStream foutObject = new FileOutputStream("filenmae.txt");
				ObjectOutputStream outputObject = new ObjectOutputStream(foutObject);
				outputObject.writeObject(objectName);
				outputObject.close();
				foutObject.close();
		}
		catch(IOException exception){
			exception.printStackTrace();
		}
	}
}
```

Deserialization
```java
import java.io.Serializable;
public class ClassName implements Serializable {
	// data members
	// member function implmentation
}
// Main function
public class MainClassName {
	public static void main(String[] args) {
		ClassName objectName = new ClassName()
		try{
			ObjectInputStream outputIn = new ObjectInputStream(new FileOutputStream("filenmae.txt"))
			ClassName e3=(ClassName)outputIn.readObject();
			outputIn.close();
		}
		catch(IOException exception){
			exception.printStackTrace();
		}
	}
}
```


``` java
// A serialization demo.
import java.io.*;
public class SerializationDemo {
	 public static void main(String[] args) {
	 // Object serialization
		 try ( ObjectOutputStream objOStrm =
			 new ObjectOutputStream(new FileOutputStream("serial")) )
		 { // serial is the file name
			 MyClass object1 = new MyClass("Hello", -7, 2.7e10);
			 System.out.println("object1: " + object1);
			 objOStrm.writeObject(object1);
		 }
		 catch(IOException e) {
			 System.out.println("Exception during serialization: " + e);
		 }
		 // Object deserialization
		 try ( ObjectInputStream objIStrm =
			 new ObjectInputStream(new FileInputStream("serial")) )
		 { 
			 MyClass object2 = (MyClass)objIStrm.readObject();
			 System.out.println("object2: " + object2);
		 }
		 catch(Exception e) {
			 System.out.println("Exception during deserialization: " + e);
		 }
	 }
}
```

Assuming the `SerializationDemo` program, this sequence adds a deserialization filter to the code that reads a `MyClass` object. It ensures that `objIStrm` will deserialize only a `MyClass` object. An attempt to deserialize any other class will cause an exception at runtime.
**Why Use `ObjectInputFilter`?*
- **Prevents deserialization attacks** (e.g., `java.io.Serializable`-based exploits).
- **Restricts deserialization of unexpected classes**
- **Controls memory usage** (limits object size, array length, etc.)
- **Improves security when deserializing untrusted data**.
```java
// Object deserialization with a filter.
try ( ObjectInputStream objIStrm =
	new ObjectInputStream(new FileInputStream("serial")) )
{
 // Create and add a simple deserialization filter.
	ObjectInputFilter myfilter =
	ObjectInputFilter.Config.createFilter("MyClass;!*");
	objIStrm.setObjectInputFilter(myfilter);
	MyClass object2 = (MyClass)objIStrm.readObject();
	System.out.println("object2: " + object2);
}
catch(Exception e) {
	System.out.println("Exception during deserialization: " + e);
}
```

## Anonymous Inner Classes
An anonymous inner class is one that is not assigned a name.
```java
public class AnonymousInnerClassDemo extends Frame {
 String msg = "";
  public AnonymousInnerClassDemo() { // constructor
	// Anonymous inner class to handle mouse pressed events. AWT
	addMouseListener(new MouseAdapter() {
		 public void mousePressed(MouseEvent me) {
			 msg = "Mouse Pressed.";
			 repaint();
		 }
	 });
	}
	public void paint(Graphics g) {
		 g.drawString(msg, 20, 80);
	 }
	public static void main(String[] args) {
	 AnonymousInnerClassDemo appwin = new AnonymousInnerClassDemo();
	 appwin.setSize(new Dimension(200, 150));
	 appwin.setTitle("AnonymousInnerClassDemo");
	 appwin.setVisible(true);
 }
}
```

There is one top-level class in this program: `AnonymousInnerClassDemo`.

Its constructor calls the `addMouseListener()` method. Its argument is an expression that defines and instantiates an anonymous inner class.

The syntax `new MouseAdapter(){...}` indicates to the compiler that the code between the braces defines an anonymous inner class. Furthermore, that class extends `MouseAdapter`.

This new class is not named, but it is automatically instantiated when this expression is executed.

Because this anonymous inner class is defined within the scope of `AnonymousInnerClassDemo`, it has access to all of the variables and methods within the scope of that class.

Therefore, it can call the repaint( ) method and access msg directly. instead of having to pass those values to its constructor if it were not an inner class.
Another Example:
```java
public static void main(String[] args) {
	// Anonymous inner class implementing Runnable
	Runnable task = new Runnable() {
		@Override
		public void run() {
			System.out.println("Thread is running...");
		}
	};
	Thread thread = new Thread(task);
	thread.start();
}}
```


# CH - 2: Systems Programming
What are Stream? sequence of data.
- is a logical container of data that allows us to read from and write to it.
- streams are the sequence of data that are read from the source and written to the destination.
- The stream-based IO operations are faster than normal IO operation

**Java I/O streams**
---
**I. Fundamental Stream Concepts**
1.  **`InputStream`**: An abstract superclass for all byte input streams, providing the basic methods to read raw bytes from a source.
2.  **`OutputStream`**: An abstract superclass for all byte output streams, providing the basic methods to write raw bytes to a destination.
---
**II. Byte Streams (for raw binary data)**
3.  **`FileInputStream`**: Reads raw bytes directly from a file.
4.  **`FileOutputStream`**: Writes raw bytes directly to a file.
5.  **`ByteArrayInputStream`**: Reads raw bytes from an in-memory byte array.
6.  **`ByteArrayOutputStream`**: Writes raw bytes to an in-memory byte array that dynamically grows.
7.  **`BufferedInputStream`**: Adds a buffer to an `InputStream` to improve performance by reducing physical I/O operations.
8.  **`BufferedOutputStream`**: Adds a buffer to an `OutputStream` to improve performance by reducing physical I/O operations.
9.  **`DataInputStream`**: Reads primitive Java data types (like int, double) and modified UTF-8 Strings from a byte stream in a machine-independent way.
10. **`DataOutputStream`**: Writes primitive Java data types and modified UTF-8 Strings to a byte stream in a machine-independent way.
---
**III. Character Streams (for text data)**

11. **`Reader`**: An abstract superclass for all character input streams, providing the basic methods to read characters.
12. **`Writer`**: An abstract superclass for all character output streams, providing the basic methods to write characters.
13. **`InputStreamReader`**: A bridge that decodes bytes from an `InputStream` into characters, specifying the character encoding.
14. **`OutputStreamWriter`**: A bridge that encodes characters into bytes and writes them to an `OutputStream`, specifying the character encoding.
15. **`BufferedReader`**: Adds a buffer to a `Reader` for efficient character reading and provides convenient `readLine()` method.
16. **`PrintWriter`**: Writes formatted character data to a `Writer` or `OutputStream`, offering `print()`/`println()` methods and optional auto-flushing.
---
---

Java provides two types of streams:.
**Byte-based Stream** 
- devised to transmit 8bit of data. / binary files
- Two abstract classes
	1. `InputStream` : byte stream based input operations
	2. `OutputStream`: byte stream based Output operations
**Character-based Stream** 
- devised to transmit 16bit of data. / text files
- Two abstract classes
	1. `Reader` : class used for character stream based input operations
	2. `Writer`: class used for character stream based output operations

Binary file's I/O are more efficient to process than text files I/O, because binary file I/O does not require encoding and decoding.

There are many inbuilt classes that implement these abstract classes.

Input Stream

| Methods              | Description                                                                               |
| -------------------- | ----------------------------------------------------------------------------------------- |
| `int available()`    | It reads the next byte from the input stream.                                             |
| `int read()`         | It reads the next byte from the input stream.                                             |
| `int read(byte[] b)` | It reads a chunk of bytes from the input stream and store them in its byte array, b.      |
| `void close()`       | It closes the input stream and also frees any resources connected with this input stream. |
| `skip()`             | skips and discards the specified number of bytes from the input stream                    |
| `markSupported()`    | checks if the mark() and reset() method is supported in the stream                        |
| `mark()`             | marks the current position in the input stream                                            |
| `reset()`            | returns the control to the point in the stream where the mark was set                     |
Output Stream

| Methods                | Description                                                                                |
| ---------------------- | ------------------------------------------------------------------------------------------ |
| `void write(int n) `   | It writes byte(contained in an int) to the output stream.                                  |
| `void write(byte[] b)` | It writes a whole byte array(b) to the output stream.                                      |
| `void flush()`         | It flushes the output steam by forcing out buffered bytes to be written out.               |
| `void close()`         | It closes the output stream and also frees any resources connected with this output stream |
Assume a file ap.txt
```java
import java.io.*;
public class SystemProgramming {
	public static void main(String args[]) {
		byte[] readAsArray = new byte[100];
		try {
			InputStream input= new FileInputStream("ap.txt");
			System.out.println("Result of available(): " + input.available());
			System.out.println("Result from read(): " + input.read());
			input.read(readAsArray);
			System.out.print("Data read from the file: ");
			String data = new String(readAsArray);
			System.out.println(data);
			input.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}
```

- `BufferedInputStream/BufferedOutputStream` can be used to speed up input and output by reducing the number of disk reads and writes.
```java title="constructors"
public BufferedInputStream(InputStream in)
public BufferedInputStream(InputStream in, int bufferSize)
public BufferedOutputStream(OutputStream out)
public BufferedOutputStream(OutputStreamr out, int bufferSize)
```
## File
is a named location that can be used to store related information.
is directory a file?
- yes a Special kind of file.
- is a collection of files and subdirectories.
- Java application needs to be able to handle files.
Operations
- Create
-  Delete
-  Write
-  Updating
The File class in `java.io` represents a reference to a file or directory.
The File class does not specify how information is retrieved from or stored in files; it describes the properties of a file itself.
To create a file: 
```java
File (String pathname)  // e.g. `File file = new File(String pathName);`
File (String directoryPath, String filename)  
// e.g. `File file = new File(String absolutePathname, String filename);
File (URI uri) // e.g. `File file = new File(URI urlPathName);`
File(File dirObj, String filename);

// Methods
boolean canRead(), canWrite(), exists(), isFile(), isDirectory(), isAbsolute()
String getAbsolutePath()
String getName() // name of the file or directory
String getPath() 
String getParent() // parent Directory of the file
long length() // length in bytes // if file is directory: NULL
long lastModified()
String[] list() // list of directory contents // NULL if file is not directory
```

#### How File is Accessed? "File Descriptors"
The operating system produces and maintains an entry to represent the file whenever the user opens input/output streams. called "`File Descriptors`"
- are number that uniquely identifies an open file in a computer’s operating system.
- Commonly used in to store it in `FileInputStream` or `FileOutputStream`.
- File descriptors has Fields and Methods  `java.io.FileDescriptor`
	- Fields: 
		→ `Err`: is a handle to the standard error stream. 
		→ `In`: is a handle to the standard input stream. 
		→ `Out`: is a handle to the standard output stream 
	- Methods: 
		→ `sync()`: It synchronizes all the system buffers with the underlying system. 
		→ `valid()`: This method is advantageous in checking the validity of the file descriptor object.
```java
FileDescriptor filedesctiptor = null;
// String "SOFTWARE ENG"
byte[] data2write = { 83, 79, 70, 84, 87, 65, 82, 69, 32, 69, 78, 71 };
try {
	FileOutputStream out = new FileOutputStream("output.txt");
	filedesctiptor = out.getFD()
	out.write(data2write);
	// USe of sync() : to sync data to the source file
	filedesctiptor.sync();
} catch (Exception except) {
	except.printStackTrace();
} finally {
	if (out != null) out.close();
}
```

- In java, there multiple ways to read data from a file and to write data to a file. 
- Different ways: 
1. Using Byte Stream (`FileInputStream` and `FileOutputStream`) 
2. Using Character Stream (`FileReader` and `FileWriter`)

##### `FileInputStream` 
```java
FileInputStream input = new FileInputStream(stringPath);
FileInputStream input = new FileInputStream(File fileObject);
// both throw FileNotFoundException, w/c is subclaass of IOException
```
	Methods
```java
read(byte[]? , int start?, int length?) // IOException
finalize() // → ensures that the close() method is called
getChannel() //returns the object of FileChannel associated with input stream
getFD() //→ returns the file descriptor associated with the input stream
mark() //→ mark the position in input stream up to which data has been read
reset() //→ returns the control to the point in the input stream where the mark was set
close()
```
```java
try {
	FileInputStream fi= new FileInputStream("file.txt");
	// Assume the file has "The Storm is Coming!"
	System.out.println(fi.read());
	int idx = fi.read();
	while(idx != -1) {
		System.out.println(idx); // Result ?
		idx = fi.read();
	}
}catch(Exception excpt){
	System.out.println(excpt);
}
```

##### `FileOutputStream` 
```java
FileOutputStream output = new FileOutputStream(stringPath, boolean append?);
FileOutputStream output = new FileOutputStream(File fileObject, boolean app?);
```
	Methods
```java
write(byte[]? , int start?, int length?)
finalize() // → ensures that the close() method is called
getChannel() //returns the object of FileChannel associated with output stream
getFD() //→ returns the file descriptor associated with the output stream
getBytes() //→ method used in the program converts a string into an array of bytes.
```
```java
try {
	FileOutputStream output = new FileOutputStream("output.txt");
	// byte[] array = data.getBytes();
	// Writes byte to the file
	output.write(data.getBytes());
	// output.write(32);
	output.flush();
	output.close();
}
catch (Exception e) {
	e.getStackTrace();
}
```



##### `FileReader`
```java
FileReader reader = new FileReader(stringPath);
FileReader reader = new FileReader(File fileObject);
//
int read(); // (char)int
```

##### `FileWriter`
```java
FileWriter write = new FileWriter(stringPath);
FileWriter write = new FileWriter(File fileObject);
// both will create a file if not exist
```
	Methods
```java
write( char[]? )
write(String data)
getEncoding() // type of encoding that is used to store data in the file
```
```java
try {
	FileReader charReader = new FileReader("section.txt");
	charReader.read(array);
	System.out.println(array);
	charReader.close();
}
catch (Exception e) {
	System.out.println(e);
}
```


### What are Directories?
- container for multiple files.
- File Class in `java.io` package. ↓ has methods to create a directory! → `mkdir()`
	- Instantiate the File class and passing the path
	- Invoke the `mkdir()` method using the above created file object.
	- Invoke the `delete()` method using the above file object.
```java
File file = new File("./folder");
boolean dir = file.mkdir();
if (dir) {
	System.out.println("D: Successfuly created");
} else {
	System.out.println("Failed to create");
}
// 
String[] list();
File[] listFiles(); istFiles(FilenameFilter FFObj); istFiles(FileFilter FObj)
```

Consistency and security is critical in computing!
- Specially on concurrent/parallel programming.
- While reading/writing to a file  → Ensure Data Integrity

**File Locking**
is a way of locking files while being used by some processes;
The Java `java.nio` API enables locking of the file at the operating system level.
Two Kind of Locks
- _Exclusive locks_ also known as write `locks()`
- _Shared locks_ also referred to as read locks

java `FileChannel` provides to method 
- `lock()` method : acquires an exclusive lock on entire file 
- `lock(long position, long size, boolean shared)`
- can be used to acquire a lock on the given part or section of a File
These two methods will block until the lock is obtained. 
- `tryLock()` method: acquires an exclusive lock on entire file,
- `tryLock(long position, long size, boolean shared)`
- can be used to acquire a lock on the given part or section of a File.
	- they don’t block and they return immediately.

**Exclusive Lock**
- To create a `FileChannel` directly via the static open method:
- The `FileLock` instance represents a lock on the file or a region of the file
Syntax:
```java
import java.nio.channels.FileChannel;
FileChannel channel = FileChannel.open(path, openOptions)
```
To get an exclusive lock, use a writable `FileChannel`.
use `getChannel()` methods of a `FileOutputStream` or a `RandomAccessFile`.

```java
FileChannel channel = FileChannel.open(path, StandardOpenOption.APPEND) //using open mehod
try (FileOutputStream fOutS = new FileOutputStream(path);) // using FileOutputStream
{	FileChannel channel = fOutS.getChannel();
	FileLock lock = channel.lock()) {
	// write to the channel
	channel.close();
	file.close();
}
try (RandomAccessFile file = new RandomAccessFile(path, "rw");){
	FileChannel channel = file.getChannel();
	FileLock lock = channel.lock()) {
	// write to the channel
}
```

**Shared Lock**
- are also called read locks.
- to get a read lock, we must use a readable `FileChannel`.
```java
import java.nio.channels.FileChannel;
try (FileChannel channel = FileChannel.open(path, StandardOpenOption.READ);
	FileLock lock = channel.lock(0, Long.MAX_VALUE, true)) {
	// read from the channel
}
try (FileInputStream fileInputStream = new FileInputStream(path);
	FileChannel channel = fileInputStream.getChannel();
	FileLock lock = channel.lock(0, Long.MAX_VALUE, true)) {
	// read from the channel
}
try (RandomAccessFile file = new RandomAccessFile("/tmp/testfile.txt", "r");
	FileChannel channel = file.getChannel();
	FileLock lock = channel.lock(0, Long.MAX_VALUE, true)) {
	// read from the channel
}
```


#### Memory-mapped I/O
A technique for accessing hardware devices from a computer program by mapping device registers into the computer's address space, allowing them to be accessed as if they were normal memory locations.
To use memory-mapped I/O in Java, you first need to create a memory-mapped buffer.
`java.nio.MappedByteBuffer`
```java
// example mapping a file channel to memory using the map method.
public class MemoryMappedIOExample { 
  public static void main(String[] args) throws Exception { 
		RandomAccessFile file = new RandomAccessFile("example.txt", "rw"); 
		FileChannel channel = file.getChannel(); 
		// Map the file into memory  
		MappedByteBuffer buffer = channel.map(FileChannel.MapMode.READ_WRITE, 0, 
     channel.size());
		// Write to the buffer 
		buffer.putChar('H'); 
		buffer.putChar('e'); 
		buffer.putChar('l'); 
		buffer.putChar('l'); 
		buffer.putChar('o'); 
		// Flush changes to disk 
		buffer.force(); 
		// Read from the buffer 
		buffer.position(0); 
		while (buffer.hasRemaining()) { System.out.print(buffer.getChar()); } 
		// Unmap the buffer 
		channel.close(); 
		file.close(); 
	} }
```


**What are PROCESSES ?**
**Process Class**
an abstract class defined in the `java.lang` package that encapsulates the runtime information of a program in execution.
two ways of creating java processes 
- Invoking the `exec()` method in the Runtime instance
- By using `ProcessBuilder.start()` method.
The processes class has method
- `int exitValue()` : Exits code returned from the process executed;
- Reads/writes output, error, and input streams to and from the process.
	- `InputStream getErrorStream()`
	- `InputStream getInputStream()`
	- `OutputStream getOutputStream()`
- `Boolean isAlive()`: Checks to see if the invoking process is still running.
- `void destroy()`: to Kill Process
- `Process destroyForcibly()` : to kill more forcefully

**Runtime Class**
- which encapsulates the runtime environment of the program.
- class cannot be instantiated
	”get a reference to the Runtime of the currently running program”
- static method called `Runtime.getRuntime()`

Write a simple Java program to open an application as a `vscode` editor and close automatically after 10sec.
```java
import java.lang.*;
import java.util.concurrent.TimeUnit;
public class NetbeandProcessDemo {
	public static void main(String[] args) throws Exception {
		Runtime runvscode = Runtime.getRuntime();
		Process vscodePrc = runvscode.exec("vscode");
		vscodePrc.waitFor(10, TimeUnit.SECONDS);
		vscodePrc.destroy();
	}
}
```

The `ProcessBuilder` Class
- is instantiated to manage a collection of process attributes.
- To create a process → `start()`
- not safe that much
- has two constructor
	- `ProcessBuilder(List<String> command)`
		the command to be executed, along with command line arguments, is passed in a list of strings.
	- `ProcessBuilder(String... command)`
		the command and the command line arguments are specified through the `varargs` parameter.
```java
try {
	ProcessBuilder pb = new ProcessBuilder("cal", "2023");
	final Process p = pb.start();
	BufferedReader br = new BufferedReader(new 
		InputStreamReader(p.getInputStream()));
	String line;
	while ((line = br.readLine()) != null) {
		System.out.println(line);
	}
} catch (Exception ex) {
	System.out.println(ex);
}
```


### Pipes and Signals
To communicate between processes.
Pipes allow you to send data between two processes.
you can use the `PipedInputStream` and `PipedOutputStream` classes to implement pipes. 
```java
import java.io.*; 
public class PipeExample { 
  public static void main(String[] args) throws IOException { 
    // Create a PipedInputStream and a PipedOutputStream 
    PipedInputStream in = new PipedInputStream();    
    PipedOutputStream out = new PipedOutputStream(in); 
    // Write some data to the output stream    
    out.write("Hello, world!".getBytes());
   // Read the data from the input stream 
   byte[] buffer = new byte[1024]; 
   int bytesRead = in.read(buffer); 
   String message = new String(buffer, 0, bytesRead);
   System.out.println(message);
   // Close the streams out.close(); 
   in.close(); 
   }
}
```
Signals allow you to send notifications between processes. In Java, you can use the Signal class to send and receive signals.
However, note that signal handling is platform-specific and may not work on all operating systems.
```java
import sun.misc.Signal; 
import sun.misc.SignalHandler; 
public class SignalExample { 
   public static void main(String[] args) throws InterruptedException { 
     // Create a signal handler 
     SignalHandler handler = new SignalHandler() { 
	    @Override 
	    public void handle(Signal signal) { 
	      System.out.println("Received signal: " + signal.getName());
	   }
	};
    // Register the signal handler for the TERM signal    
    Signal.handle(new Signal("TERM"), handler);
    // Wait for the TERM signal
    Thread.sleep(Long.MAX_VALUE);
  } 
}
```
Also note that the Signal class is not part of the public API and may not be available on all platforms.


### SEQUENTIAL-ACCESS TEXT FILES
A **sequential-access text file** in Java is a file where you read or write data character by character, from start to finish, in order. You can't skip around; you have to go through it in order.

**Example**: Writing an Object to a Text File
You write an object to a text file by converting its data into a string and then writing that string. It's not the object's binary form, but a human-readable text representation.

```java

class Person {
  private String name; private int age;
  public Person(String name, int age) { this.name = name; this.age = age; }
  public String toCsvString() { return name + "," + age; }
}

public class WritePersonData {
  public static void main(String[] args) {
    Person person1 = new Person("Alice", 30); String fileName = "people.txt";
    try (PrintWriter writer = new PrintWriter(new FileWriter(fileName, true))) {
      writer.println(person1.toCsvString());
      System.out.println("Person data written to " + fileName);
    } catch (IOException e) { 
	    System.err.println("Error: " + e.getMessage()); }
  }
  
		// Example of reading the file
		System.out.println("\n--- Content of " + fileName + " ---");
		try (BufferedReader reader = new BufferedReader(new FileReader(fileName))) {
			String line;
			while ((line = reader.readLine()) != null) {
					System.out.println(line);
			}
		} catch (IOException e) {
				System.err.println("Error reading file: " + e.getMessage());
		}
}
}
// using Scanner class to read

public class ReadLinesFromFile {
  public static void main(String[] args) {
    String fileName = "people.txt"; // The file to read

    // Use try-with-resources to ensure the Scanner is closed
    try (Scanner fileScanner = new Scanner(new File(fileName))) {
      System.out.println("Reading all lines from '" + fileName + "':");
      while (fileScanner.hasNextLine()) {
        String line = fileScanner.nextLine(); // Read the entire line
        System.out.println(line); // Print the line
      }
      System.out.println("\nFinished reading file.");
    } catch (FileNotFoundException e) {
      System.err.println("Error: The file '" + fileName + "' was not found.");
    }
  }
}
```

This code creates a `Person` object, converts its data into a simple string (e.g., "Alice,30"), and writes that string to `people.txt`. The `FileWriter(fileName, true)` ensures that if the file exists, the data is added to the end rather than overwriting it. `PrintWriter` makes writing text lines easy.

##### Updating Sequential Text Files
You can't directly change data in the middle of a sequential text file. If you need to **update** a line, **delete** one, or **insert** a new one, you generally have to:

1.  **Read** the original file line by line.
2.  **Make changes** (or skip lines for deletion) in your program.
3.  **Write** the modified or unchanged lines to a *new temporary file*.
4.  **Replace** the old file with the new temporary file.

Think of it as rewriting the entire document, not just editing a sentence.


# CH - 3: Persistence and Database

### 3.1 Overview of the database connectivity
Database is an organized collection of data.
DBMS - provides mechanisms for storing, organizing, retrieving and modifying.
e.g. Microsoft SQL Server, Oracle, Sybase, Informix, PostgreSQL, MySQL.

#### JDBC API | Java Database Connectivity
JDBC is a Standard API that enables Java applications to interact with databases. (a bridge)
- `java.sql` package contains classes and interfaces for JDBC API.
- it uses JDBSC drivers to communicate with the database.

1. Type 1 driver - aka JDBC-ODBC bridge driver
	- converts JDBC method calls to ODBC function calls
2. Type 2 driver - Native-API Driver
	- converts JDBC to native calls of the database API
3. Type 3 driver - Network Protocol driver
	- converts JDBC directly or indirectly to vendor specific database protocol.
4. Type 4 driver - Thin driver
	- converts JDBC directly to vendor-specific database protocol

 JDBC Driver is an interpreter that translates JDBC method calls to vendor-specific database commands. it implements interfaces in`java.sql` package.


Two Packages 
- `java.sql`: an API to access and process the data stored in a database
- `javax.sql`: an API for the server side for accessing and processing the data from the databases.

1. `DriverManager` facility
	- `DriverManager` class - connects with the driver.
	- `SQLPermission` class - provides permission when running with a Security Manager.
	- `Driver interface` - API for registering and connecting drivers.
	- `DriverPropertyInfo` class - provides properties for a JDBC driver.
2. Sending SQL statements to a database
	- `Statement`, `PreparedStatement`, `CallableStatement` - used to call database stored procedures.
- A `CallableStatement` is an interface in Java's JDBC (Java Database Connectivity) API that is used to execute SQL stored procedures. Stored procedures are precompiled collections of SQL statements and optional control-of-flow statements stored under a name and processed on the database server.
	- `Connection interface` - creates statements and manages connections.
	- `Savepoint` - provides save points in a transaction.
3. Retrieving and updating the results of a query
	- `ResultSet` interface. - provides methods for retrieving and manipulating the results of executed queries,
		- it maintains a cursor that points to the current row in the result set.
		- `Cursor` - is a temporary work area created in the system memory when a SQL statement is executed.
		- contains information on a select statement and the rows of data accessed by it.
		- The '`next()`' method moves the cursor to the next row. returns false if no more rows.
		- `ResultSet` methods -> `Type get<Type>(int colIndex), Type get<Type>(string colName), int findColumn(String colName)` e.g. `int getInt()`
4. Standard mappings for SQL types to classes and interfaces
	- `Array` interface - mapping for SQL ARRAY.
	- `Blob` interface - mapping for SQL BLOB.
	- `Clob` interface - mapping for SQL CLOB.
	- `Date` class - mapping for SQL DATE.
	- `NClob` interface - mapping for SQL NCLOB.
5. Custom mapping an SQL user-defined type (UDT) to a class
	- `SQLData` interface - specifies the mapping of a UDT to an instance of this class.
	- `SQLInput` interface - reads UDT attributes from a stream.
	- `SQLOutput` interface - writes UDT attributes back to a stream.
6. Exceptions
	- `SQLException` - thrown by most methods when there is a problem accessing data.
	- `SQLWarning` - indicates a warning.
	- `DataTruncation` - indicates that data may have been truncated.
	- `BatchUpdateException` - indicates that not all commands in a batch update executed successfully.

using JDBC to connect and manage a database has 5 steps. 
- Register the Driver class 
- Create connection
- Create statement
- Execute queries
- Close connection

1. **Register the Driver class**:
   - Before you can connect to a database, you need to register the JDBC driver. It acts as a bridge between Java and the database. 
   - Approach 1: using the `Class.forName()` method, which dynamically loads the driver class into memory. For example, for a MySQL database, you might use `Class.forName("com.mysql.cj.jdbc.Driver");`.
   - Approach 2: `DriverManager.registerDriver()` method
```java
try { // Driver driverObjectName = new drivername; 
	Driver myDriver = new com.mysql.cj.jdbc.Driver();
	DriverManager.registerDriver(myDriver);}
```

2. **Create connection**:
   - This is done using the `DriverManager.getConnection()` method, which takes a database URL, username, and password as arguments. The database URL specifies the location and type of the database. For example:
```java
Connection connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/mydatabase", "username", "password");
// getConnection(String url)
// getConnection(String url, String Properties)
// getConnection(String url, String username, String password)
```
Connection Interface - is a session between a Java application and a specific database.

3. **Create statement**:
   - `Statement` object is used to execute SQL queries. You can create a `Statement` using the `createStatement()` method of the `Connection` object. For example:
```java
Statement statement = connection.createStatement();
PreparedStatement pS = connection.prepareStatement("SQL")
```
- Alternatively, you can use `PreparedStatement` for parameterized queries or `CallableStatement` for stored procedures.
```java
//(3) methods for the transaction management
setAutoCommit(boolean status)
commit()
rollback()
```
use Statement Object to execute
- `boolean execute (String SQL)`→ true if a `ResultSet` object can be retrieved by `stmt.getResultSet()`; 
- `int executeUpdate (String SQL)`→ Returns the number of rows affected by the execution of the SQL statement.
- `executeQuery(String)` - Execute a SQL query that returns a single `ResultSet` 
```java
INSERT_DATA = "INSERT INTO sectionAB" + "(id, name, email) VALUES " + " (?, ?, ?);";
try (PreparedStatement pS = conn.prepareStatement(INSERT_DATA)) { 
pS.setInt(1, 1); pS.setString(2, "Abebe"); 
pS.setString(3, "abebe.kebede@aastu.edu.et"); 
preparedStatement.executeUpdate();} catch (SQLException e) {}
```
`ResultSet` Interface - interface provides methods for retrieving and manipulating the results of executed queries.
4. **Execute queries**:
   - Using the `Statement` object, you can execute SQL queries. For queries that return results, such as `SELECT` statements, you use the `executeQuery()` method, which returns a `ResultSet` object. For queries that update the database, such as `INSERT`, `UPDATE`, or `DELETE` statements, you use the `executeUpdate()` method. For example:
```java
ResultSet resultSet = statement.executeQuery("SELECT * FROM mytable");
```
   - You can then iterate over the `ResultSet` to process the query results.

5. **Close connection**:
   - After you have finished executing queries and processing results, it is important to close the connection to release database resources. This is typically done in a `finally` block to ensure that the connection is closed even if an exception occurs. You should also close the `Statement` and `ResultSet` objects. For example:
```java
finally {
	if (resultSet != null) resultSet.close();
	if (statement != null) statement.close();
	if (connection != null) connection.close();
}
```

```
Step 1: Load and register the driver 
Step 2:Connect to the database
Step 3: Create statements
Step 4: Execute statements
Step 5: Process the Result
Step 6: close ResultSet and Statement
Step 7: Close the connection
```


```java
import java.sql.*;
public class DisplayAuthors {
public static void main(String[] args) {
	try {
		// Load the JDBC driver
		Class.forName("com.mysql.cj.jdbc.Driver");
		// Connect to the database
		String url =
		"jdbc:mysql://localhost:3306/Books?user=myuser&password=mypassword";
		Connection conn = DriverManager.getConnection(url);
		// Create a Statement object to execute SQL queries
		Statement stmt = conn.createStatement();
		// Execute the query and store the results in a ResultSet object
		ResultSet rs = stmt.executeQuery("SELECT authorId, firstName, 	           	lastName FROM Authors");
		// Iterate through the ResultSet and display the data
		while (rs.next()) {
		int authorId = rs.getInt("authorId");
		String firstName = rs.getString("firstName");
		String lastName = rs.getString("lastName");
		System.out.println("Author ID: " + authorId + ", First Name: " +
		firstName + ", Last Name: " + lastName); }
		// Close the ResultSet, Statement, and Connection objects
		rs.close();
		stmt.close();
		conn.close();
	} catch (Exception e) {
	e.printStackTrace();
} } }
```


# CH - 4: Network Programming
### Networking Basics
- **Port number** is used to uniquely identify different applications. It acts as a communication endpoint between applications.
	- **IP address + port number** = "phone number“ for service or application
- **MAC** (Media Access Control) Address is a unique identifier of NIC (Network Interface Controller).
- A protocols is a set of rules that facilitate communications between machines or hosts. e.g. HTTP, FTP, SMTP, TCP, UDP
	- **TCP (Transmission Control Protocol)**:
	  - Connection-oriented protocol.
	  - Enables two hosts to establish a connection and exchange data streams.
	  - Reliable but slower due to acknowledgments from the receiver.
	  - Uses stream-based communications.
	  - Guarantees delivery of data in the order sent.
	- **UDP (User Datagram Protocol)**:
	  - Connectionless communication.
	  - Faster but not reliable as acknowledgments are not sent.
	  - Uses packet-based communications.
	  - Does not guarantee lossless transmission.

### Introduction
Network programming refers to writing programs that execute across multiple devices (computers), in which the devices are all connected to each other using a network.
- The java.net package APIs contains a collection of classes and interfaces that provide the low-level communication details.
- java.net provides support for both TCP and UDP.

#### Socket-Level Programming
Java Socket programming is used for communication between the applications running on different JRE.
Java Socket programming can be connection-oriented or connectionless.
- TCP: `Socket` and `ServerSocket` classes are used for connection-oriented socket programming. 
- UDP: `DatagramSocket` and `DatagramPacket` classes are used for connection-less socket programming.
Send and receive data using streams.

### TCP
`ServerSocket` class for creating a server socket and `Socket` class for creating a client socket.
Sockets are the endpoints of logical connections between two hosts and can be used to send and receive data.
Network programming usually involves a server and one or more clients.

Socket Programming
- Sockets provide the communication mechanism between two computers using TCP.
- A client program creates a socket on its end of the communication and attempts to connect that socket to a server.
- When the connection is made, the server creates a socket object on its end of the communication.
- The client and server can now communicate by writing to and reading from the socket.

Client/Server Communications
The statements needed to create `sockets on a server` and a `client` are shown below.
Server
1. Create a server socket on a port
```java
ServerSocket serverSocket = new ServerSocket(8000);
//ServerSocket(int port)
//ServerSocket(int port, int backlog) // how many incoming clients to store in a wait queue.
//ServerSocket(int port, int backlog, InetAddress address) 
//ServerSocket() - unbound server socket. use the bind() method when you are ready to bind the server socket.
```
- `int getLocalPort()`: Returns the port that the server socket is listening on.
- `void setSoTimeout(int timeout)`: Sets the time-out value for how long the server socket waits for a client during the `accept()` 
- `public void bind(SocketAddress host, int backlog)`: Binds the socket to the specified server and port in the `SocketAddress` object.

2. Create a socket to connect to a client
```java
Socket socket = serverSocket.accept();
```
Client
3. Connect to the server
```java
Socket socket = new Socket(serverHost, 8000);
//Socket(String host, int port) // UnknownHostException
//Socket(InetAddress host, int port) // IA object instead of name
//Socket(String host, int port, InetAddress localAddress, int localPort)
//Socket(InetAddress host, int port, InetAddress localAddress, int localPort)
//Socket() // Use the connect() method to connect this socket to a server.
//InetAddress class represents - IP address.
```
`serverHost` is the server’s Internet host name or IP address. e.g. `localhost, www.google.com` 

Socket methods
```java
void connect(SocketAddress host, int timeout) throws IOException:  //connects the socket to the specified host.
 InetAddress getInetAddress():  //returns the address of the other computer that this socket is connected to.
int getPort():  //Returns the port the socket is bound to on the remote machine.
int getLocalPort():  //Returns the port the socket is bound to on the local machine.
SocketAddress getRemoteSocketAddress():  //Returns the address of the remote socket (socket = server.accept())
void close() throws IOException:  //Closes the socket, which makes this Socket object no longer capable of connecting again to any server
```

After the connections are established, communication can occur using I/O streams.
- Each socket has both an `OutputStream` and an `InputStream`.
- The client's `OutputStream` is connected to the server's `InputStream`, and
- The client's `InputStream` is connected to the server's `OutputStream`.
TCP is a two way communication protocol, so data can be sent across both streams at the same time.

Attempting to create a server socket on a port already in use would cause the `java.net.BindException`.

##### Data Transmission through Sockets
After the server accepts the connection, communication between the server and client is conducted the same as for I/O streams.
```java
// Server
int port = 8000;
DataInputStream in;
DataOutputStream out;
ServerSocket server;
Socket socket;

sever = new ServerSocket(port);
socket = server.accept();
in = new DataInputStream(socket.getInputStream());
out = new DataOutputStream(socket.getOutputStream());
System.out.println(in.readDouble());
out.wirteDouble(1.1);
```

```java
// Client
int port = 8000;
String host = "localhost";
DataInputStream in;
DataOutputStream out;
Socket socket;

socket = new Socket(host, port);
in = new DataInputStream(socket.getInputStream());
out = new DataOutputStream(socket.getOutputStream());
out.wirteDouble(1.1);
System.out.println(in.readDouble());
```

- Binary I/O is more efficient than text I/O because text I/O requires encoding and decoding. 
- Therefore, it is better to use binary I/O for transmitting data between a server and a client to improve performance.

##### `InetAddress` Class
```java
InetAddress getByAddress(byte[] addr)
InetAddress getByAddress(String host, byte[] addr)
InetAddress getByName(String host)
String getHostAddress()
String getHostName()
InetAddress getLocalHost()
String toString()
```

**Socket Example**: Client sends circle radius to server. Server calculates area, sends it back. Client displays the area.
Server
```java
public class CircleAreaServer {
  public static void main(String[] args) {
    final int PORT = 8000; // Server listens on this port
    try (ServerSocket serverSocket = new ServerSocket(PORT)) {
      System.out.println("Server listening on port " + PORT + "...");
      while (true) { // Server keeps running for multiple clients
        try (Socket clientSocket = serverSocket.accept();
          DataInputStream input = new DataInputStream(clientSocket.getInputStream());
          DataOutputStream output = new DataOutputStream(clientSocket.getOutputStream())) {

          double radius = input.readDouble(); // Read radius
          double area = Math.PI * radius * radius; // Calculate area
          output.writeDouble(area); // Send area
          System.out.println("Received radius: " + radius + ", Sent area: " + area);
        } catch (IOException e) {
          System.err.println("Client handling error: " + e.getMessage());
        }
      }
    } catch (IOException e) {
      System.err.println("Server startup error: " + e.getMessage());
    }
  }
}
```

Client
```java
public class CircleAreaClient {
  public static void main(String[] args) {
    final String SERVER_ADDRESS = "localhost"; // Server address
    final int PORT = 8000; // Server port

	try (Socket socket = new Socket(SERVER_ADDRESS, PORT);
		DataOutputStream output = new DataOutputStream(socket.getOutputStream())
		DataInputStream input = new DataInputStream(socket.getInputStream());
		Scanner scanner = new Scanner(System.in)) {
		    
		System.out.print("Enter circle radius: ");
		double radius = scanner.nextDouble(); // Get radius from user
		output.writeDouble(radius); // Send radius
		double area = input.readDouble(); // Read area
		System.out.println("Circle area: " + area); // Display result
	} catch (UnknownHostException e) {
	} catch (IOException e) {
	} catch (java.util.InputMismatchException e) {
	}  } }
```


### UDP Clients and Servers
UDP (User Datagram Protocol) is a connectionless transport layer protocol that is often used for applications that require low latency and do not require guaranteed delivery of packets.

In contrast to TCP, UDP does not establish a connection before transmitting data, and there is no error checking or retransmission of lost packets.

Is implemented using the `DatagramSocket` and `DatagramPacket` classes from `java.net`.
`DatagramSocket` Used to send and receive UDP packets.
- Acts like a mailbox for sending or receiving datagrams on a specific port.
`DatagramPacket` Represents the actual data being sent or received.

`DatagramSocket` class
A datagram is basically an information but there is no guarantee of its content, arrival or arrival time.
```java title=constructors
DatagramSocket() throws SocketException{}
DatagramSocket(int port) throws SocketException{}
DatagramSocket(int port, IntAddress address) throws SocketException{}
```

`DatagramPacket` class
```java
DatagramPacket(byte[] barr, int length){}
DatagramPacket(byte[] barr, int length, InetAddress address, int port){}
```


```java
//UDP Server
import java.io.*; import java.net.*; // Import necessary classes for IO and networking

public class UDPServer {
  public static void main(String[] args) {
    try {
      DatagramSocket serverSocket = new DatagramSocket(1234); // Create UDP socket, bind to port 1234
      System.out.println("UDP Server running on port 1234"); // Confirm server started
      byte[] receiveData = new byte[1024]; // Buffer for incoming data
      DatagramPacket receivePacket = new DatagramPacket(receiveData, receiveData.length); // Packet to hold received data
      while (true) { // Loop indefinitely to receive packets
        serverSocket.receive(receivePacket); // Block until received
        String message = new String(receivePacket.getData(), 0, receivePacket.getLength()); // Extract message from packet
        InetAddress clientAddress = receivePacket.getAddress(); // Get client's IP address
        int clientPort = receivePacket.getPort(); // Get client's port
        System.out.println("Received: \"" + message + "\" from " + clientAddress + ":" + clientPort); // Print received message info
        String response = "Hello, client!"; // Define response message
        byte[] sendData = response.getBytes(); // Convert response to bytes
        DatagramPacket sendPacket = new DatagramPacket(sendData, sendData.length, clientAddress, clientPort); // Create response packet
        serverSocket.send(sendPacket); // Send the response packet
        System.out.println("Sent: \"" + response + "\" to " + clientAddress + ":" + clientPort); // Confirm response sent
      }
    } catch (IOException e) { e.printStackTrace(); } // Handle network errors
  }
}
```

```java
//UDP Client
import java.io.*; import java.net.*;
public class UDPClient {
public static void main(String[] args) {
try {
	DatagramSocket clientSocket = new DatagramSocket();
	String message = "Hello, server!";
	byte[] sendData = message.getBytes();
	InetAddress serverAddress = InetAddress.getByName("localhost");
	int serverPort = 1234;
	DatagramPacket sendPacket = new DatagramPacket(sendData, sendData.length,
	serverAddress, serverPort);

	clientSocket.send(sendPacket);
	System.out.println("Sent: " + message + " to " + serverAddress + ":" + 
	serverPort);

	byte[] receiveData = new byte[1024];
	DatagramPacket receivePacket = new DatagramPacket(receiveData, receiveData.length);
	clientSocket.receive(receivePacket); // Block until a response
	String response = new String(receivePacket.getData(), 0, receivePacket.getLength());
	InetAddress server = receivePacket.getAddress();
	int port = receivePacket.getPort();
	System.out.println("Received message: " + response 	+ " from " + server + ":" + port);
	clientSocket.close();
} catch (IOException e) { e.printStackTrace(); } }
}
```

#### URL
The URL provides a reasonably intelligible form to uniquely identify or address information on the Internet.
Within Java’s network class library, the URL class provides a simple, concise API to access information across the Internet using URLs.

**Format** 
A URL specification can be broken down into four main components:
1. **Protocol**: Specifies the protocol to use, followed by a colon (`:`).
2. **Host Name/IP Address**: Identifies the host, enclosed between double slashes (`//`) and followed by a slash (`/`) or optionally a colon (`:`).
3. **Port Number (Optional)**: Specified after a colon (`:`) following the host name, and before a slash (`/`).
4. **File Path**: The path to the specific resource or file.
e.g. `https://www.example.com:8080/path/to/resource` 

Java's `URL` class has several constructors, each of which can throw a `MalformedURLException`
```java
URL(String spec);
URL(String protocol, String host, int port, String file)
URL(String protocol, String host, String file)
URL(URL context, String spec)
//URL context = new URL("https://www.example.com"); 
//new URL(context, "/path/to/resource")
URL(String protocol, String host, int port, String file, URLStreamHandler handler)
```

Commonly used methods of the Java `URL` class:
- `getProtocol()`, `getHost()`, `getPort()` 
- **`getFile()`**: Returns the file name of the URL. // path to resource
- **`openConnection()`**: Returns an instance of `URLConnection` associated with this URL.
- `toExternalForm()`: the full URL string

To access the actual bits or content information of a URL, you create a `URLConnection` object from it, using its `openConnection( )` method, like this:
- `url.openConnection()` returns `URLConnection` and throws an `IOException`.

**`URLConnection` class** 
- Represents a communication link between a URL and an application.
- Enables reading and writing data to the resource specified by the URL.
- Provides methods like `getInputStream()` to access and display URL data.
- Can throw an `IOException` during operations.

```java
try{
	URL url = new URL("http://www.javatpoint.com/java-tutorial");
	URLConnection urlcon = url.openConnection();
	InputStream stream = urlcon.getInputStream();
	int i;
	while((i=stream.read())!=-1) System.out.print((char)i);
} catch(Exception e){ System.out.println(e); }
```

##### `HttpURLConnection` class
- is http specific `URLConnection`.
You can get information of any HTTP URL such as header information, status code, response code etc.
It is subclass of `URLConnection` class.
`HttpURLConnection huc = (HttpURLConnection) url.openConnection();` 

### Serving Multiple Clients
- A server can handle multiple clients simultaneously.
- Each client connection is managed by a separate thread.
- Use a loop to accept connections and create a new thread for each client:
```java
while (true) {
    Socket socket = serverSocket.accept(); // wait blocking until conn
    Thread thread = new ThreadClass(socket);
    thread.start();
}
class ThreadClass extends Thread {
	ThreadClass(Socket s){
	}
	run(){}
}
```

#### Sending and Receiving Objects
Sending and receiving objects over socket streams involves serialization and deserialization:
1. **Serialization**: Convert objects to a byte stream.
```java
ObjectOutputStream out = new ObjectOutputStream(socket.getOutputStream());
out.writeObject(myObject);
```
2. **Deserialization**: Convert byte streams back to objects.
```java
ObjectInputStream in = new ObjectInputStream(socket.getInputStream());
MyObject receivedObject = (MyObject) in.readObject();
```
- Objects must implement `Serializable`.
- Handle exceptions like `IOException` and `ClassNotFoundException`.


# CH - 5: Remote Procedure Call & Remote Method Invocation
### Overview
RPC and RMI are both mechanisms for invoking functions or methods located on remote computers.
**RPC (Remote Procedure Call):** 
- Generic concept that refers to any Mechanism for calling procedures across a network.
- Client sends a request to a server to execute a function and receive results.
- Works with various languages and protocols (e.g., XML-RPC, JSON-RPC, `gRPC`).
**RMI (Remote Method Invocation):** 
- Java-specific RPC implementation. part of Java’s core API.
- Enables Java objects in one JVM to invoke methods on objects in another JVM.
- Uses Java serialization for parameter passing and return values.
- Simplifies creating distributed Java applications.

Both RPC and RMI facilitate distributed applications, with RMI tailored for Java.

### Key Components of RMI Architecture

1. **Client**:
	- The client is the application that invokes methods on a remote object. It interacts with the remote object through a local stub.
2. **Server**:
	- The server hosts the remote objects. It creates instances of remote objects and makes them available to clients through the RMI registry.
3. **Remote Interface**:
	- An interface that declares the methods that can be invoked remotely. It extends `java.rmi.Remote` and each method must declare `RemoteException` in its throws clause.
4. **Remote Object**:
	- An instance of a class that implements the remote interface. This object resides on the server and its methods can be invoked by clients.
5. **Stub**:
	- A client-side proxy for the remote object. The stub implements the same set of remote interfaces as the remote object. It handles the communication with the skeleton on the server side.
	- When the client invokes a method on the stub, the stub marshals the parameters, sends the request to the server, waits for the response, and `unmarshals` the result before returning it to the client.
6. **Skeleton**:
	- A server-side entity that interacts with the remote object. It receives method invocations from the stub, invokes the corresponding methods on the remote object, and sends the results back to the stub.
	- It receives requests from the client, `unmarshals` (deserializes) the parameters, invokes the remote method, marshals (serializes) the result, and sends it back to the client.
	- is generated automatically by the RMI runtime system.
7. **RMI Registry**:
	- A naming service that allows clients to look up remote objects by name. The server binds remote objects to the RMI registry, and clients look up these objects using the registry.
	- Each time the server creates an object, it registers this object with the RMI registry (using `bind()` or `reBind()` methods) using a name that identifies the object.
	- Objects are registered using a unique name known as bind name.
	- Clients can then look up the remote object in the RMI Registry by its name, using its bind name(using `lookup()` method) and the registry returns a reference to the object.
	- It can be started as a separate process or can be started within the server process itself.
		- when separate, it listens on a specific port for incoming requests from clients.
8. **Transport Layer**:
   - Handles the actual communication between the client and server. It uses Java's object serialization to marshal and unmartial parameters and return values.
   - This layer is abstracted by RMI.


### How RMI Works
##### Server-Side:
1. **Create Remote Interface**:
   - Define an interface that extends `java.rmi.Remote`. This interface declares the methods that can be invoked remotely.
   ```java
   public interface MyRemoteInterface extends Remote {
       String remoteMethod() throws RemoteException;
   }
   ```

2. **Implement Remote Interface**:
   - Create a class that implements the remote interface. This class contains the actual implementation of the remote methods.
   ```java
   public class MyRemoteObject implements MyRemoteInterface {
       @Override
       public String remoteMethod() throws RemoteException {
           return "Hello, RMI!";
       }
   }
   ```

3. **Create RMI Registry**:
   - Start the RMI registry, which acts as a directory service for remote objects.
```java
try { Registry registry = LocateRegistry.createRegistry(1099);
```

4. **Bind Remote Object**:
   - Create an instance of the remote object and bind it to the RMI registry.
```java
MyRemoteObject remoteObject = new MyRemoteObject();
registry.bind("rmi://localhost/MyRemoteObject", remoteObject);
//registry.bind("MyRemote", remoteObject);
```

##### Client-Side:
1. **Lookup Remote Object**:
   - The client looks up the remote object from the RMI registry using its URL.
```java
MyRemoteInterface remoteInterface = (MyRemoteInterface)Naming.lookup("rmi://localhost/MyRemoteObject");
```

2. **Invoke Remote Method**:
   - The client invokes methods on the remote object as if it were a local object.
```java
String result = remoteInterface.remoteMethod();
System.out.println(result);
```
##### Communication:
- **Serialization**: RMI uses Java's serialization mechanism to pass parameters and return values between the client and server.
- **Stub and Skeleton**: RMI generates stubs (client-side proxies) and skeletons (server-side entities) to handle communication. The stub communicates with the skeleton to invoke methods on the remote object.
##### Error Handling:
- `RemoteException`: Handle exceptions that occur during remote method invocation, such as network issues or remote object unavailability.
```java
try {
	String result = remoteInterface.remoteMethod();
	System.out.println(result);
} catch (RemoteException e) {
	System.err.println("Error invoking remote method: " + e.getMessage());
}
```

- `NotBoundException`: Handle exceptions that occur if the remote object is not found in the RMI registry.
```java
try {
	MyRemoteInterface remoteInterface = (MyRemoteInterface) 
		Naming.lookup("rmi://localhost/MyRemoteObject");
} catch (NotBoundException e) {
	System.err.println("Remote object not found: " + e.getMessage());
}
  ```

RMI simplifies the development of distributed Java applications by providing a straightforward way to invoke methods on remote objects, with built-in support for serialization and error handling.

The RMI (Remote Method Invocation) architecture is a framework that enables Java objects to invoke methods on remote Java objects. It is designed to facilitate communication between distributed Java applications. Here's a breakdown of the RMI architecture:

##### Full Example

✅ **Overview** 
We'll build a basic RMI application where:
* The **server** exposes a remote method: `sayHello()`.
* The **client** connects remotely and invokes this method.

📁 Project Structure
```yaml
RMIExample/
├── common/
│   └── Hello.java   # Remote interface (shared between client and server)
├── server/
│   ├── HelloImpl.java    # Server-side implementation
│   └── RMIServer.java    # Server main class
└── client/
    └── RMIClient.java    # Client main class
```

1. 🔄 `common/Hello.java` — Remote Interface
```java
package common;
import java.rmi.Remote;
import java.rmi.RemoteException;
public interface Hello extends Remote {
    String sayHello() throws RemoteException;
}
```

2. 🖥️ `server/HelloImpl.java` — Remote Object Implementation
```java
package server;
import common.Hello; import java.rmi.RemoteException;
import java.rmi.server.UnicastRemoteObject;
public class HelloImpl extends UnicastRemoteObject implements Hello {
    protected HelloImpl() throws RemoteException {
        super();
    }
    @Override
    public String sayHello() throws RemoteException {
        return "Hello from the RMI server!";
    }
}
```

3. 🖥️ `server/RMIServer.java` — Start the RMI Server
```java
package server;
import common.Hello; import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;

public class RMIServer {
    public static void main(String[] args) {
        try {
            Hello hello = new HelloImpl();
                                                // default RMI port
            Registry registry = LocateRegistry.createRegistry(1099); 
            registry.rebind("HelloService", hello);
            System.out.println("RMI Server is running...");
        } catch (Exception e) {
            e.printStackTrace();
        }    }   }
```

4. 💻 `client/RMIClient.java` — Connect to the Server and Call the Remote Method
```java
package client;

import common.Hello;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
public class RMIClient {
    public static void main(String[] args) {
        try {
            Registry registry = LocateRegistry.getRegistry("localhost", 1099);
            Hello hello = (Hello) registry.lookup("HelloService");
            // Hello hello = (Hello) Naming.lookup("HelloService");
            String response = hello.sayHello();
            System.out.println("Server says: " + response);
        } catch (Exception e) {
            e.printStackTrace();
        }  }  }
```

***🛠️ How to Compile and Run*** 
1. **Compile everything:** 
```bash
# From RMIExample root
javac common/Hello.java
javac -cp . server/HelloImpl.java server/RMIServer.java
javac -cp . client/RMIClient.java
```

2. **Run the server:** 
```bash
java -cp . server.RMIServer
```

3. **In a separate terminal, run the client:** 
```bash
java -cp . client.RMIClient
```

Notes
* Make sure `common/Hello.java` is accessible to both server and client.
* No `rmic` step is needed in modern Java (8+), since dynamic stubs are used.
* Ensure `java.rmi.registry` runs within the same JVM (or start it separately if needed).


# CH-6 : Threads
**Multitasking** 
1. **Process-Based Multitasking** 
   - Managed by the OS scheduler.  
   - **Heavyweight**—each process has its own memory space.  

2. **Thread-Based Multitasking** 
   - A **thread** is the smallest executable unit within a process.  
   - A single program can perform multiple tasks at once (e.g., downloading while rendering UI).  
   - **Lightweight** - threads share the same memory space, reducing overhead.
- Threads are faster to create/switching than processes. 

## Introduction
**Multithreading** in java is a process of executing multiple threads simultaneously.
**Multitasking** is when multiple processes share common processing resources such as a CPU.
- *Multithreading* enables multiple tasks in a program to be executed concurrently.
- A thread is a lightweight sub-process, the smallest unit of processing.
Multi-threading extends the idea of multitasking into applications where you can subdivide specific operations within a single application into individual threads.

### Multitasking
1. Multitasking is a process of executing multiple tasks  simultaneously. We use multitasking to utilize the CPU.
2. Multitasking can be achieved in two ways:
	- Process-based Multitasking (Multiprocessing)
	- Thread-based Multitasking (Multithreading)

**3. Process-based Multitasking (Multiprocessing)**
Each process has an address in memory. (each process allocates a separate memory area).
- A process is heavyweight.
- Cost of communication between the process is high.
- Switching from one process to another requires some time for saving and loading registers, memory maps, updating lists, etc.
**2. Thread-based Multitasking (Multithreading)**
 - Threads share the same address space.
 - Lightweight and switching is fast.

#### Advantages of multithreading
Threads are independent, so it doesn't affect other threads if an exception occurs in a single thread.
It is more responsive to user input– GUI application can interrupt a time-consuming task.
All threads managed by the JVM share memory space and can communicate with each other

| Process                                                                                                 | Thread                                                                                                                               |
| ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Process is a program in execution.                                                                      | A thread is a subset (part) of theprocess.                                                                                           |
| A process consists of multiple threads.                                                                 | A thread is a smallest part of the process that can execute concurrently with other parts (threads) of the process.                  |
| A process has its own address space                                                                     | A thread uses the process’s address space and shares it with the other threads of that process.                                      |
| A process can communicate with other process by using inter- process communication                      | A thread can communicate with other thread (of the same process) directly by using methods like `wait()`, `notify()`, `notifyAll()`. |
| A process does not have control over the sibling process; it has control over its child processes only. | Threads have control over the other threads of the same process.                                                                     |

## What is Thread in JAVA?
It is a separate path of execution. They are independent so exceptions are isolated.
They use a shared memory area.
A thread is the flow of execution, from beginning to end of a task.
Threads can be executed simultaneously in multiprocessor systems.

#### Thread Class
Thread class provides constructors and methods to create and perform operations on a thread.

Threads can be created by using two mechanisms:
1. Implementing `java.lang.Runnable` interface
	- It has only one method named: `public void run()` - is used to perform action for a thread.
	- You need to implement a `run()` method provided the Runnable interface.
	- Then we instantiate a Thread object and call start() method on this object.
2. Extending `java.lang.Thread` class
	- Thread class implements Runnable interface.
	- `run()` method must be overridden
	- `run()` is called when execution of the thread begins
	- A thread terminates when `run()` returns
	- `start()` method invokes `run()`.
	- Calling `run()` does not create a new thread

Example 1: Implementing the Runnable interface.
```java
public class Task implements Runnable { // Runnable
	public Task(...) {...}
	public void run() { /* Do something */ }
	public static void main(){
		Task task = new Task();
		Thread thread = new Thread(task);   thread.start();
	}
}
```

Example 2: Extending the Thread Class.
- We create an object of our new class and call `start()` method to start the execution of a thread. `start()` calls `run()`.
```java
public class TaskThread extends Thread { // Thread
	public TaskThread(...){...}
	public void run() { /* Do something */ }
	public static void main(){
		TaskThread task = new TaskThread();
		task.start();
	}
}
```

```java
+Thread()
+Thread(task: Runnable)
+start(): void
+isAlive(): boolean
+setPriority(p:int): void // from 1 - 10 : def=5
+join(): void             // waits for the thread to finish
+sleep(millis:long): void
+yield(): void        // temporarily pauses and allow other threads to execute
+interrupt(): void
```

#### The `run()` method
- It specifies how to perform the task.
- It is automatically invoked by the JVM. and shouldn't be invoked manually.
- invoking it directly doesn't create a thread it just runs like a regular method.

#### The static `yield()` method
Used to temporarily release time for other threads.
Example:
```java
public void run() {
	for (int i = 1; i <= lastNum; i++){
		System.out.print(" " + i);
		Thread.yield();
	}
}
```

#### The static `sleep(mill)` method
`sleep(long milliseconds)` is used to sleep a thread for the specified amount of time.
Example:
```java
public void run() {
	for (int i = 1; i <= lastNum; i++) {
		System.out.print(" " + i);
		try {
			if (i >= 50) Thread.sleep(1);
		} catch (InterruptedException ex) { }
	}
}
```
Every time a number (>= 50) is we printed, the thread is put to sleep for 1 millisecond.

#### The `join()` method
Used to force one thread to wait for another thread to finish.
```java
class PrintNum implements Runnable{
	private int lastNum;
	public PrintNum(int n) { lastNum = n; }
	public void run() {
		Thread thread4 = new Thread(new PrintChar('c', 40));
		thread4.start();
		try {
			for (int i = 1; i <= lastNum; i++) {  
				System.out.print(" " + i);
				if (i == 50) thread4.join();
			}
		}
		catch (InterruptedException ex) {}
	}
}
```
The numbers after 50 are printed after thread `printA` is finished.

### Life Cycle of a Thread (Thread States)
A thread can be in one of five states: **New**, **Ready/Runnable**, **Running**, **Blocked**, or **Finished/Terminated**.
The life cycle of the thread in java is controlled by the JVM.
![[Pasted image 20250521130007.png]]

Ready/Runnable doesn't mean running. The OS has to allocate CPU time to it to run.
- At thread can enter the ready state after running if its given CPU time expires or its `yield()` method is called.
- A thread can enter blocked state for several reason.
	- it may have invoked the `join()`, `sleep()` or `wait()` method. or waiting for an I/O operation to finish. (namely WAITING/TIMED_WAITING)
	- It is then reactivated when that action is reversed (put into Ready state).
- Finally a thread is Finished if it completes the execution of its `run()` method.

#### Thread methods
```java
isAlive() // true if ready/blocked/running and false if new/finished
interrupt() // if ready or running it sets the interrupt bit 
isInterrupted()
// Deprecated Methods since java 2 // known to be inherently unsafe.
stop()
suspend()
resume()
```
- We should just assign null to the Thread variable to indicate that it is stopped rather than use `stop()`.
- `interrupt()` during blocked/waiting it awakes the thread and `InterruptedException` is thrown.

#### Thread Priority
We can increase or decrease the priority of any thread by using the `setPriority` method, and you can get the thread’s priority by using the `getPriority` method. (1-10)

The Thread class has three int constant priorities.
```java
public static int MIN_PRIORITY = 1
public static int NORM_PRIORITY = 5 // default
public static int MAX_PRIORITY = 10
```

The JVM always picks the currently runnable thread with the highest priority.
If all runnable threads have equal priorities, each is assigned an equal portion of the CPU time in a circular queue. This is called **round-robin** scheduling.

### Thread Scheduling in JAVA
Most operating systems use time slicing for threads of equal priority.
**Thread scheduler** in java is the part of the JVM that decides which thread should run.
The thread scheduler mainly uses preemptive or time slicing scheduling to schedule the threads.
- **Preemptive scheduling**: Higher-priority threads preempt lower-priority ones.
- **Time slicing**: Threads run for a fixed time slice before switching (reenters ready state).

Only one thread per core runs at a time.
**Starvation/Contention**: High-priority threads may indefinitely delay low-priority threads.
- **Solution**: High-priority threads should periodically call `sleep()` or `yield()` to allow others to execute.

### JAVA Thread Pool
A **thread pool** is a managed collection of reusable worker threads that execute tasks concurrently, improving efficiency by:
- Reducing thread creation/destruction overhead.  
- Controlling the number of concurrent threads.  

**Why Use a Thread Pool?**
1. **Efficiency** – Reusing threads avoids the cost of creating new ones per task.
2. **Performance** – Prevents system overload by limiting active threads.
3. **Scalability** – Better handles large numbers of tasks compared to "one thread per task".
4. **Resource Management** – Avoids **thrashing** (excessive thread creation degrading performance).

**Key Components in Java** 
1. **`Executor` Interface** – Base interface for executing tasks.
2. **`ExecutorService` Interface** – Extends `Executor` with lifecycle management (e.g., shutdown, task submission).
3. **`ThreadPool` Implementations**: 
   - **`FixedThreadPool`** – Fixed number of threads.
   - **`CachedThreadPool`** – Dynamically adjusts thread count.
   - **`ScheduledThreadPool`** – Supports delayed/periodic tasks.
   - `SingleThreadPool` - A pool with one thread, executing tasks sequentially.

**How It Works**
- Tasks (`Runnable`/`Callable`) are submitted to the pool.
- Idle threads pick tasks from a **task queue**.
- If no threads are free, tasks wait in the queue.

### Creating Executors
To create an Executor object, use the static methods in the Executors class.
If a thread completes executing a task, it can be reused to execute another task.
If a thread terminates due to a failure and there are tasks waiting, a new thread will be created to replace it.
A thread in a **cached pool** will be terminated if it has not been used for 60 seconds.
A cached pool is efficient for many short tasks.
**Example**:
```java
ExecutorService pool = Executors.newFixedThreadPool(4); // 4 threads  
// submit: Returns Future(like Promise in js), can handle exceptions
pool.submit(() -> System.out.println("Task running"));
// execute: No return, exceptions go to UncaughtExceptionHandler
pool.execute(new PrintNum(100)); // one on the PPT
pool.shutdown(); // Graceful termination, wait for tasks to finish

// Other methods
shutdownNow(): List<Runnable> // Shuts down the executor immediately and Returns a list of unfinished tasks.
isShutdown(): boolean;  //Returns true if the executor has been shutdown
isTerminated(): boolean // Returns true if all tasks in the pool are terminated
```

**When to Use?** 
- High-volume short-lived tasks (e.g., web servers, batch processing).
- Need for controlled concurrency (avoiding resource exhaustion).

Steps to be follow:
1. Create a task (Runnable object) to execute
2. Create Executor Pool using Executors
3. Pass tasks to Executor Pool
4. Shutdown the Executor Pool (graceful)

### Thread Synchronization
Thread Synchronization is the capability to control the access of multiple  threads to any shared resource.
Example: two unsynchronized threads accessing the same bank account may cause conflict. 
```java
balance    Task 1                           Task 2
0         newB = balance + 1           
0                                    newB = balance + 1
1         balance = newB
1                                    balance = newB // reseted the prev step
```
- this is a race condition example.
A **thread-safe** class does not cause a race condition in the presence of multiple threads.

#### The `Synchronized` Keyword
- give exclusive access to one thread at a time to code that manipulates a shared object.
To prevent race conditions, only **one thread** should access a **critical region** (a part of the program that modifies shared data) at a time.  
- The `synchronized` keyword ensures that only **one thread** can execute a method or block at a time.
```java
public synchronized void deposit(double amount) { balance += amount; }
```
- This forces other threads to **wait** until the current thread finishes executing the method. 


#### Synchronized Methods in Java
A synchronized method acquires a lock before it executes.
**1. Synchronized Instance Methods**
- **Lock:** On the **object instance** (`this`).  
- **Effect:** - Only **one thread** can execute any `synchronized` instance method of the same object at a time.
**Example:**  
```java
public synchronized void instanceMethod() {
	// Only 1 thread per object can run this at a time
}
```

**2. Synchronized Static Methods**  
- **Lock:** On the **class itself** (`ClassName.class`).  
- **Effect:** 
  - Only **one thread** can execute any `synchronized` static method of the class at a time.  
  - Blocks all threads across **all instances** of the class.  
- **Example:** 
```java
public static synchronized void staticMethod() {
	// Only 1 thread globally can run this at a time
}
```

| Feature         | Instance Synchronized Method                   | Static Synchronized Method                  |
| --------------- | ---------------------------------------------- | ------------------------------------------- |
| **Lock On**     | Object (`this`)                                | Class (`ClassName.class`)                   |
| **Blocks**      | Other instance methods on the **same object**  | All static methods across **all instances** |
| **Concurrency** | Different objects → No blocking                | All threads contend for **same class lock** |

#### Synchronized Blocks
- **Purpose:** Synchronize **only a part** of a method (not the whole method).  
- **Syntax:**  
```java
synchronized (lockObject) { 
	// Critical section 
}
```  
- **Benefits**:
	-  **Finer control** (better performance).  
	- **Flexible locking** (can use any object as lock).  
- **Example**:
```java
synchronized (account) {
	account.deposit(1); 
}
```  
- **Key Idea:** Locks `lockObject`, executes the block, then releases the lock.  

**Use when:** You need thread safety for **specific lines**, not the entire method.  

#### Inter-Thread Communication
**Purpose:**
Allows synchronized threads to **coordinate and cooperate**, especially in shared resource scenarios.

**Object Class Methods (Classic Approach)** 
1. **`wait()`** – Pauses the thread until `notify()` or `notifyAll()` is called.
2. **`notify()`** – Wakes **one** waiting thread.
3. **`notifyAll()`** – Wakes **all** waiting threads.

🛑 **Rules**:
* Must be used inside a **`synchronized`** block/method.
* Otherwise, throws `IllegalMonitorStateException`.

📦 **Use Case**: Producer-consumer, deposit-withdraw patterns.

 **Bank Account Example (with wait/notify)** 
* **Withdraw Thread**:
```java
synchronized (account) {
	while (balance < amount) account.wait();  // Wait for sufficient funds
	balance -= amount;
}
```

* **Deposit Thread**:
```java
synchronized (account) {
	balance += amount;
	account.notifyAll();  // Wake up waiting withdrawers
}
```

**Condition (Modern Approach)** 
* From `java.util.concurrent.locks.Condition`
* Used with `ReentrantLock` (instead of `synchronized`)
* Offers better control: `await()`, `signal()`, `signalAll()`

**Condition-Based Version**

```java
Lock lock = new ReentrantLock();
Condition newDeposit = lock.newCondition();

lock.lock();
try {
	while (balance < amount) newDeposit.await();  // Wait if not enough
	balance -= amount;
} finally {
	lock.unlock();
}

// Deposit task
lock.lock();
try {
	balance += amount;
	newDeposit.signalAll();  // Notify withdrawers
} finally {
	lock.unlock();
}
```

✅ **Why Use Conditions?** 
* More flexible than `wait/notify` 
* Can have **multiple conditions** per lock
* Avoids mistakes tied to monitor locks

### Semaphores in Java
**Purpose:** Controls access to shared resources by limiting concurrent threads. 

**How It Works:** 
- **Permits:** A semaphore has a fixed number of "permits" (like tokens).  
- **Thread Access:** 
  - **`acquire()`** → Takes a permit (waits if none available).
  - **`release()`** → Returns the permit when done.

**Key Features:**  
- **Fairness Policy:** Optional (`true` = first-come-first-serve).  
- **Dynamic Permits:** Count decreases on `acquire()`, increases on `release()`.  

**Example:**  
```java
+Semaphore(numberOfPermits:int); // default fairness policy is false
+Semaphore(numberOfPermits: int, fair: boolean);
+acquire(): void
+release(): void
//ex
Semaphore semaphore = new Semaphore(3); // 3 permits  

// Thread task:
semaphore.acquire();  // Wait for permit  
try {
    // Access shared resource (max 3 threads at a time)  
} finally {
    semaphore.release();  // Release permit  
}
```  
- Fairness = true -> use FIFO order to prevent starvation. slower due to queue maintenance.
- Fairness = false -> a thread may "cut in line" and get a permit ahead of others. faster.
**Use Case**:
- Rate-limiting API calls.  
- Connection pool management.  

### Deadlock in Java
A situation where **two or more threads** block each other forever, waiting for locks held by one another.
**Example Scenario**:
- **Thread 1** holds `Lock A` and waits for `Lock B`.  
- **Thread 2** holds `Lock B` and waits for `Lock A`.  
- **Result:** Both threads freeze indefinitely.  

**How to Avoid Deadlock?** 
- **Lock Ordering:** Always acquire locks in a **fixed global order** (e.g., `Lock A` → `Lock B`).  
- **Timeouts:** Use `tryLock()` with timeout to avoid indefinite waits.  

**Key Points:**  
- Deadlocks **halt program execution** silently.  
- Prevention is better than debugging!

**Example (Avoiding Deadlock with Ordering):**  
```java
Thread 1: synchronized(A) { synchronized(B) { ... } }  
Thread 2: synchronized(B) { synchronized(A) { ... } }  // Deadlock
// Correct: Both threads acquire locks in SAME order (A → B)
Thread 1: synchronized(A) { synchronized(B) { ... } }  
Thread 2: synchronized(A) { synchronized(B) { ... } }  
```  
Once Thread 1 acquires a lock on object1, Thread 2 has to wait for a lock on object1. Thus, Thread 1 will be able to acquire a lock on object2 and no deadlock will occur.

# CH - 7 : GUI
There are three basic things that are necessary to develop a graphical user interface
- The GUI components **sets and containers**: - form the interface
	- buttons, labels, check boxes, etc.
- **Component arrangement (Layout)**:- the scheme where by the UI components are arranged to create the interface.
- **Response to user requests**: - the act of associating actions to user requests, known as 'events.

### Implementing GUIs in Java
The Java Foundation Classes (JFC) Encompass a group of features for constructing graphical user interfaces (GUI).
JFC encompasses the following APIs:
- **Abstract Window Toolkit (AWT)**: native GUI components.
- **Swing**: light weight GUI components.
- **2D**: rendering two-dimensional shapes, text, and images.

##### Using AWT Components
AWT is Java’s original set of classes for building GUIs:
* Uses **OS-specific peer components** (e.g., `java.awt.Button` has a peer `java.awt.peer.Button`).
* **Heavyweight**.
* **Not truly portable**: looks and lays out inconsistently on different OSs due to the underlying display management system.
* AWT is fine for **simple graphical user interfaces**, but **not for comprehensive GUI projects**.

Every GUI component is a subclass of the AWT **`Component` class** (except for menus):
* **Controls**: allow simple user input.
* **Labels**: display text.
* **Containers**: arrange other components.
* Use **Canvases**: for custom components.

**Peers and Platform Independence** 
UI components that have peers are called **heavyweight** because:
* They display in their **own, separate windows**, which makes them costly to use.
* They have to be **rectangular** and can't have see-through backgrounds.
* You **can't create new classes based on them** (they can't be sub-classed).

AWT is prone to platform-specific bugs because its peer-based approach depends heavily on the underlying operating system.

**How AWT works**:
When a Java program creates an AWT component, Java AWT then creates and displays a **native component, or peer**.

**Using Peers**:
* The platform controls the component's appearance.
* This leads to inconsistencies in how things look and behave across different systems.
* Interfacing with the native platform is also prone to errors.

##### AWT Limitations
AWT offers a basic, but limited, graphical interface because it translates visual components into platform-specific "peers".
* This means the look and feel of components are defined by the operating system, not by Java.
* AWT components are "heavyweight" due to their reliance on native code resources.

**Key Missing Features**:
* **Fewer component types**: Important components like tables and trees are missing.
* **Lack of rich component features**: Example, buttons do not support pictures.
* **No extensibility**: You cannot easily inherit from and reuse existing AWT components.

**Problems due to Native Peers**:
* Components can **look or even act differently on various platforms** due to OS variations.
* The look and feel of each component was **fixed and could not be changed**.

##### Lightweight Components
AWT 1.1 introduced lightweight components that:
* Are **contained within a heavyweight component's window**.
* **Do not have peers**.
* **Render in their container's window**, not their own.
* **Avoid performance penalties** and can have transparent backgrounds.

Almost all Swing components are lightweight, extending either `java.awt.Component` or `java.awt.Container`.

##### What is Swing?
With Java 2, Swing components replaced AWT, offering a more **robust, versatile, and flexible** GUI library.
* Swing includes a **rich set of modern components** like tables, lists, trees, buttons, and labels.
* It supports **numerous look and feels**, including custom ones.
* Swing is part of the **Java Foundation Classes (JFC)**.

**Features**:
* **Pluggable Look and Feel**: Allows programmatic control over appearance.
* **Data Transfer**: Supports drag and drop, cut, copy, and paste functionalities.
```java
import java.awt.*;
import javax.swing.*;
```

**Swing Philosophy** 
* **Richer Component Set**: Replaces the AWT Component Set and adds more complex components.
* **Swing Components Java-Based**: If problems occur, they're consistent across all platforms.
    * For this reason, Swing components that don't rely on native GUI are referred to as **lightweight components**.

**The Swing Containment Hierarchy**: Typically has at least:
* **Top-Level Container**: The root container holding everything together (e.g., `JApplet`, `JFrame`, `Window`).
* **Intermediate Container**: Simplifies positioning of atomic components (e.g., `JPanel`, `JScrollPane`).
* **Atomic Component**: A self-sufficient component not holding others (e.g., `JButton`, `JLabel`).

Swing components are less dependent on the target platform and use fewer native GUI resources.

##### GUI Class Hierarchy (Swing)
Swing components are organized into a class hierarchy.
* All Swing components, except for top-level containers (`JFrame`, `JDialog`, `JApplet`), inherit from **`JComponent`**.
* `JComponent` itself extends `java.awt.Container`, which in turn extends `java.awt.Component`. This shows that Swing is built on top of AWT, but overrides much of its behavior to be lightweight.

* **`java.lang.Object`**
    * **`Dimension, Font, FontMetrics, Color, Graphics`** 
    * **`java.awt.Component`**: The root of all AWT components.
        * **`java.awt.Container`**: A component that can hold other components.
            * **`javax.swing.JComponent`**: The base class for almost all lightweight Swing components. This is where many common features like borders, tooltips, and keyboard bindings are handled.
                * Specific Swing components like `JButton`, `JLabel`, `JPanel`, `JTextField`, `JTable`, `JTree`, etc., all extend `JComponent`.
            * **Top-Level Containers**: These are the main windows of a Swing application and are heavyweight. They are directly extended from AWT classes and do not extend `JComponent`.
                * `java.awt.Window`
                    * `java.awt.Frame`
                        * `javax.swing.JFrame` (for standalone applications)
                    * `java.awt.Dialog`
                        * `javax.swing.JDialog` (for pop-up windows)
                * `java.awt.Applet`
                    * `javax.swing.JApplet` (for applets embedded in web pages)


**Description of Classes** 
* **Object**: The root of all classes in Java.
* **Component**: Represents a visual object on screen that can interact with users. Defines basic methods for all Swing classes.
* **Container**: Extends `Component` by adding the ability to hold other components.
* **Window**: A specialized container with a border, title bar, control buttons (min/max/close), repositioning, and optional resizing.
* **Frame**: An AWT `Window` type, improved by `JFrame`, serving as the base for Java GUI applications.
* **`JFrame`**: The Swing version of `Frame`. Most Swing applications use at least one `JFrame`.
* **`JComponent`**: The base for all other Swing components, except for frames.
* **`JPanel`**: Used to organize and control the layout of other components (labels, buttons, text fields, etc.). Panels are often added to a `JFrame` to display their contents.
* **`JLabel`**: Creates a label that displays a simple text value.


**AWT vs. Swing** 
Swing does not replace AWT; it is **built on top of it**.
* All original AWT components are **heavyweight**, while corresponding Swing components are **lightweight**.
* Swing component names begin with "J" (e.g., `JButton` vs. `Button`).

| Feature           | Java AWT                   | Java Swing                                     |
| :---------------- | :------------------------- | :--------------------------------------------- |
| **Platform**      | Platform-dependent         | Platform-independent                           |
| **Weight**        | Heavyweight                | Lightweight                                    |
| **Look and Feel** | No pluggable look and feel | Supports pluggable look and feel               |
| **Components**    | Fewer components           | More powerful components (tables, lists, etc.) |
| **Architecture**  | Doesn't follow MVC         | Follows MVC (Model-View-Controller)            |

**Frames** 
* A `Frame` is a window not contained within another.
	* It serves as the base for holding other UI components in Java GUI applications.
* `JFrame` is the application window class.
* `JFrame` is special: it draws the window and interacts with the operating system.
* When a `JFrame` is created, a `contentPane` (an inner container) is automatically created.
* We draw graphics on the **`contentPane`**, not directly on the `JFrame`.

```java
import java.awt.*;
import javax.swing.*;
// The Calc class extends JFrame to create a GUI window
public class Calc extends JFrame {
    // Constructor to set up the JFrame
    public Calc() {
        // Get the content pane of the JFrame
        Container cp = getContentPane();
        // Exit the application when the window is closed
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        // Set the layout manager to FlowLayout
        cp.setLayout(new FlowLayout());
        // Set the title of the window
        setTitle("My First Calculator");
        // Set the size of the window
        setSize(1000, 700);
    }
    // Main method to launch the GUI
    public static void main(String[] args) {
        // Create an instance of Calc
        Calc trial = new Calc();
        // Make the window visible
        trial.setVisible(true);
    }
}
```


**`JPanel` Class** 
A `JPanel` is a type of **container** designed to hold groups of components.
* The usual way to display controls is to add them to a panel, then add the panel to the frame.
* You can add controls directly to the frame, if preferred.
* can be nested

**Constructors**:
* `JPanel()`: Creates a new panel.
* `JPanel(LayoutManager layout)`: Creates a panel with a specified layout manager (default is `FlowLayout`).

**Key Methods**:
* `void add(Component c)`: Adds a component to the panel.
* `void remove(Component c)`: Removes a component from the panel.
* `void setLayout(LayoutManager layout)`: Sets the layout manager for arranging components on the panel.
* `void setLocation(int x, int y)`: Sets the panel's top-left corner position (0,0 is screen top-left).
* `void setSize(int width, int height)`: Sets the panel's width and height.

```java
import java.awt.*;
import javax.swing.*;

public class Calc extends JFrame {
    private JPanel entryPanel;
    private JPanel answerPanel;

    public Calc() {
        Container cp = getContentPane();
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        cp.setLayout(new FlowLayout());
        cp.setBackground(Color.white);
        setTitle("My Funky Calculator");
        setSize(1000, 700);
        entryPanel = new JPanel();
        entryPanel.setBackground(Color.orange);
        answerPanel = new JPanel();
        answerPanel.setBackground(Color.yellow);
        cp.add(entryPanel);
        cp.add(answerPanel);
    }
    public static void main(String[] args) {
        Calc trial = new Calc();
        trial.setVisible(true);
    }
}
```


**`JComponent`** 
`JComponent` is the **base class for all Swing components** except top-level containers.
* `JComponents` do not extend their AWT counterparts (e.g., `JButton` is not a subclass of `Button`).
* `JComponents` are also **containers**.
* `JComponent` subclasses present information or interact with the user (e.g., `JLabels`, `JButtons`, `JTextFields`).

**Using Labels** 
A `JLabel` is a component that simply **displays text**.
* You have **complete control over text appearance** (font, size, bold, italic, underlined, color, etc.).

**Constructors**:
* `JLabel()`: Creates a new label with no initial text.
* `JLabel(String text)`: Creates a new label with specified text.

**Methods**:
* `String getText()`: Returns the text displayed by the label.
* `void setText(String text)`: Sets the text displayed by the label.

```java
import java.awt.*;
import javax.swing.*;

public class MyTest extends JFrame {
    JLabel myLabel = new JLabel("Hello, World!");
    public MyTest() {
        super("MyTest"); // set title
        setSize(350, 100);
        getContentPane().add(myLabel);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setVisible(true);
    }
    public static void main(String args[]) {
        MyTest m = new MyTest();
    }
}
```

**Creating Buttons** 
`JButton` is a common component for user clicks.
- **Constructors**: `JButton()` (empty), `JButton(String text)`.
- **Key Methods**: `getText()`, `setEnabled(boolean value)`, `setText(String text)`, `setVisible(boolean value)`.

**`JTextField` - `JPasswordField`** 
These are single-line areas for user input or displaying text.
* **Constructors**: `JTextField(int columns)`, `JTextField(String text)`, `JTextField(String text, int columns)`.
* **Key Methods**: `getColumns()`, `setColumns(int)`, `getText()`, `setText(String text)`, `setEditable(boolean editable)`.

**`JPasswordField`** 
A specialized text field for passwords.
* **Constructor**: `JPasswordField(String text [not placeholder], int columns)`.
* **Key Methods**: `setEchoChar(char echo) (set the displayed char)`, `getPassword(): char[]`.

**`TextArea`** 
A component for accepting multiple lines of text.
* **Constructors**: `JTextArea()`, `JTextArea(int rows, int columns)`, `JTextArea(String s, int rows, int columns)`.

**`JComboBox`** 
A drop-down list for user selection, possibly with typing.
* **Constructor**: `JComboBox(String str[])`.
* **Key Methods**: `getSelectedItem()`, `getSelectedIndex()`, `setMaximumRowCount(int n)`.

```java
import java.awt.*;
import javax.swing.*;public class Calc extends JFrame {
    private JTextField num1 = new JTextField("1st Number", 10), 
    private num2 = new JTextField("2nd Number", 10);
    private JLabel answerLabel = new JLabel("Answer");
    private JComboBox<String> operation = new JComboBox<>(new String[]
	    {"ADDITION", "SUBTRACTION", "MULTIPLICATION", "DIVISION"});
    private JButton calculate = new JButton("Calculate");
    private JButton quit = new JButton("Quit");
    private JPanel entryPanel = new JPanel(), answerPanel = new JPanel();

    public Calc() {
        setTitle("My Funky Calculator"); setSize(1000, 700); 
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        Container cp = getContentPane(); cp.setLayout(new FlowLayout()); 
        cp.setBackground(Color.WHITE);
        entryPanel.add(new JLabel("Let's Calculate!")); entryPanel.add(num1); 
        entryPanel.add(num2); entryPanel.add(operation); 
        entryPanel.add(answerLabel);
        answerPanel.add(calculate); answerPanel.add(quit); 
        cp.add(entryPanel); cp.add(answerPanel);

        calculate.addActionListener(e -> {
            try {
                double a = Double.parseDouble(num1.getText()), 
                double b = Double.parseDouble(num2.getText()), res = 0;
                String op = (String) operation.getSelectedItem();
                switch (op) {
                    case "ADDITION" -> res = a + b;
                    case "SUBTRACTION" -> res = a - b;
                    case "MULTIPLICATION" -> res = a * b;
                    case "DIVISION" -> res = b != 0 ? a / b : Double.NaN;
                    default -> { }
                }
                answerLabel.setText("Answer: " + res);
            } catch (NumberFormatException ex) {
                answerLabel.setText("Invalid Input");
            }
        });
        quit.addActionListener(e -> System.exit(0));
    }

    public static void main(String[] args) {
        new Calc().setVisible(true);
    }
}
```


**Checkbox(`JCheckBox`)** 
`JCheckBox`, `JToggleButton`, and `JRadioButton` are **state (on/off) buttons**.

* **Constructors**: `JCheckBox(String s, Icon i, Boolean state)`, `JCheckBox(String label)`, `JCheckBox(String s, Boolean state)`.
* **Methods**: `void setSelected(boolean state)`, `boolean isSelected()`.
* `JRadioButton` and `JToggleButton` are similar.

**List (`JList`)** 
* **Constructor**: `JList(String str[])`.
* **Methods**: `int getSelectedIndex()`, `Object getSelectedValue()`, `Object[] getSelectedValues()`, `int[] getSelectedIndices()`, `setListData(ListItems)`.
* **No built-in scrollbar**: To enable scrolling, add `JList` to a `JScrollPane`.
    * **Syntax**: `container.add(new JScrollPane(obj));` (where `obj` is a `JList` object).
    * **Method**: `setVisibleRowCount(int n)`.

### Layout Managers 
Layout managers are associated with containers and **automate the positioning and sizing of UI elements**.
* They provide abstraction for consistent UI mapping across windowing systems.
* They automatically adjust component positions and sizes when elements are added or the window is resized.
* They control where components appear, their sizes, and how they react to resizing.

Every container has a layout manager. Common layout managers include:
* `FlowLayout` 
* `GridLayout` 
* `BorderLayout` 
* `CardLayout` 
* `GridBagLayout` 
* `NullLayout` 

**Hierarchy of Layout Managers**
All layout managers implement the `LayoutManager` interface.
More complex layout managers like `GridBagLayout` are often preferred for intricate layouts.
- `GridBagLayout` implements `LayoutManager2` w/c implements `LayoutManager`.

**`FlowLayout`** 
* Components are added **left-to-right**, wrapping to the next row when a row is full.
* **Constructors**: `FlowLayout()`, `FlowLayout(int align)`, `FlowLayout(int align, int hSpace, int vSpace)`.
* **Method**: `setAlignment(int align)` (e.g., `FlowLayout.LEFT`, `.CENTER`, `.RIGHT`).

**`BorderLayout`** 
* Uses **five regions**: `NORTH`, `SOUTH`, `EAST`, `WEST`, and `CENTER`.
* All extra space is given to the `CENTER` area.
* **Constructor**: `BorderLayout(int hgap, int vgap)`.
* **Method**: `void add(Component cp, String region)` (e.g., `container.add(button, BorderLayout.CENTER)`).

**`GridLayout`** 
* Creates a **grid structure** on the container.
* Every component has the **same width and height**.
* **Constructors**: `GridLayout(int rows, int cols)`, `GridLayout(int rows, int cols, int hgap, int vgap)`.
* Components are added from the **top-left cell, proceeding left-to-right** until the row is full.
    * Example: `new GridLayout(4,3);` (often used for calculator layouts).

**`CardLayout`** - another manager.

**The `GridBagLayout`** 
The `GridBagLayout` is a highly flexible layout manager.
* Rows and columns can have **variable sizes**.
* You can **join adjacent cells** for larger components.
* Components don't have to fill the entire cell, and you can specify their **alignment within cells**.

**Procedure to use `GridBagLayout`**:
1.  **Create a `GridBagLayout` object.** (You don't specify rows/columns; the manager infers them.)
2.  **Set this `GridBagLayout` as the container's layout manager.** 
3.  **For each component, create a `GridBagConstraints` object.** 
    * Set field values of `GridBagConstraints` to define the component's layout within the grid.
4.  **Add each component using `add(component, constraints)`**.

**Example**:
```java
panel.setLayout(new GridBagLayout());
GridBagConstraints constraints = new GridBagConstraints();
constraints.weightx = 100;
constraints.weighty = 100;
constraints.gridx = 0;
constraints.gridy = 2;
constraints.gridwidth = 2;
constraints.gridheight = 1;
panel.add(component, constraints);
```
* `gridx`, `gridy`, `gridwidth`, and `gridheight` define the component's location and size within the grid.
- `weightx` - The portion of extra space to allocate horizontally. The components can become wider when extra space is available
- `weighty` - The portion of extra space to allocate vertically. The components can become taller when extra space is available.
- If you set the weight to 0, then the area never grows or shrinks beyond its initial size in that direction.

**The Null Layout Manager** 
* Setting a container's layout manager to `null` allows you to **explicitly set component sizes and positions**.
```java
class NullLayout extends JFrame{
	JButton btn;
	JTextField txt;
	JComboBox jcb;
	NullLayout(){
		btn = new JButton("Ok");
		txt = new JTextField();
		jcb = new JComboBox(); Container cp = getContentPane(); cp.add(btn);
		cp.add(txt);
		cp.add(jcb);
		cp.setLayout(null);
		btn.setBounds(50, 50, 60, 30);
		txt.setBounds(50, 90, 60, 20);
		jcb.setBounds(50, 120, 60, 20);
	}
	public static void main(String args[]){
		NullLayout nl = new NullLayout();
		nl.setVisible(true);
	}
}
```


### The Java Event Handling
**Event-Driven Programming**: An **event** is a signal to the program that something has occurred. Events are generated by user actions (like mouse clicks, keystrokes) or the operating system (like a timer). 
The GUI component generating the event is called the **source object**.
##### The Delegation Event Model
This model is central to Java's event handling, providing a standard way to generate and process events. Its main advantage is the **clean separation of application logic (event processing) from user interface logic (event generation)**. Events are supported by the `java.awt.event` package.

There are three key objects in this model:
* **Event Sources**: Objects that generate events (e.g., menus, buttons, text fields). Events occur when an object's internal state changes. Sources can generate multiple events and have methods to add/remove event listeners (e.g., `addActionListener()`). A source notifies all its registered listeners.
* **Event Objects**: Objects representing a user action (e.g., mouse click). They contain a reference to the event source and other event-specific information. Event sources send event objects to their listeners. Events can be generated by user interaction (button press, key entry, item selection, mouse click) or by the system (timer, system failure). `EventObject` is the superclass, with specific event types like `ActionEvent` and `MouseEvent` as subclasses.
* **Event Listeners**: Objects that respond when an event occurs. They must be registered with one or more sources to receive specific event notifications and must implement methods to process these notifications. Listeners are **interfaces**, not classes (e.g., `class MyButtonListener implements ActionListener`).

**Listener Registration**:
A source must register listeners using methods like `<Source>.add<Type>Listener(<Type>Listener el)`.
* Example: `addKeyListener()`, `addMouseMotionListener()`.
* Sources also provide `remove<Type>Listener()` to unregister listeners.

**Listener Examples**:
* If the listener is a different class:
    ```java
    ListenerClass lc = new ListenerClass();
    JButton btnTest = new JButton("Test");
    btnTest.addActionListener(lc);
    ```
* If the listener is the same class containing the source:
    ```java
    btnTest.addActionListener(this);
    ```
    (The class must implement the appropriate Listener interface and define its methods.)

---
**GUI Class Hierarchy (Event Objects)** 
* `java.lang.Object`
    * `java.util.EventObject` (Superclass of all event objects)
        * `java.awt.AWTEvent`
            * `java.awt.event.ActionEvent`
            * `java.awt.event.ItemEvent`
            * `java.awt.event.ComponentEvent`
	            * `java.awt.event.InputEvent`
		            * `java.awt.event.MouseEvent`
		            * `java.awt.event.KeyEvent`
		            * `java.awt.event.WindowEvent`
            * ...and many other specific event types.

---
##### Common Event Types and Listeners

* **`ActionEvent`**:
    * Occurs with `JButton` clicks, `JTextField` (pressing Enter).
    * **Listener Interface**: `ActionListener` 
    * **Method**: `public void actionPerformed(ActionEvent ae)` 
    * **Key Methods**: `String getActionCommand()` (returns caption/text of source), `Object getSource()` (returns source object reference).

* **`ItemEvent`**:
    * Occurs with `JCheckBox`, `JRadioButton`, `JComboBox` when their state changes (selected/deselected).
    * **Listener Interface**: `ItemListener` 
    * **Method**: `public void itemStateChanged(ItemEvent ie)` 
    * **Key Methods**: `(event object).getSource()`, `(event object).getStateChange()` (returns `ItemEvent.SELECTED` or `ItemEvent.DESELECTED`).

* **`MouseEvent`**: Handled by two listener interfaces:
    * **`MouseListener`**: For clicks, presses, releases, enters, exits.
        * **Methods**: `mouseClicked()`, `mouseEntered()`, `mouseExited()`, `mouseReleased()`, `mousePressed()`.
    * **`MouseMotionListener`**: For mouse movement.
        * **Methods**: `mouseMoved()`, `mouseDragged()`.

* **`WindowEvent`**:
    * **Listener Interface**: `WindowListener` 
    * **Methods**: `windowClosing()`, `windowOpened()`, `windowIconified()`, `windowDeiconified()`, `windowClosed()`, `windowActivated()`, `windowDeactivated()`.

* **`KeyEvent`**:
    * **Listener Interface**: `KeyListener` 
    * **Methods**: `keyPressed()`, `keyReleased()`, `keyTyped()`.

* **`TextEvent`**:
    * Listens for any key input in a text component.
    * **Listener Interface**: `TextListener` 
    * **Method**: `public void textValueChanged(TextEvent e)`.

```java
import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class MyButtonApp extends JFrame implements ActionListener {

    private JButton clickMeButton;
    private JLabel messageLabel;

    public MyButtonApp() {
        setTitle("Button Click Example");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout()); // Simple layout manager
        clickMeButton = new JButton("Click Me!");
        // Register this class (MyButtonApp) as the listener for the button
        clickMeButton.addActionListener(this); 
        add(clickMeButton);
        messageLabel = new JLabel("Button not clicked yet.");
        add(messageLabel);
        setVisible(true);
    }
    @Override
    // This method is called automatically when an ActionEvent occurs
    public void actionPerformed(ActionEvent e) {
        // Check if the event source is our button
        if (e.getSource() == clickMeButton) {
            messageLabel.setText("Button was clicked!");
            System.out.println("Button clicked!"); // Also print to console
        }
    }
    public static void main(String[] args) {
        // Create an instance of our JFrame to run the application
        SwingUtilities.invokeLater(() -> new MyButtonApp());
    }
}

// optional way to implement this // anonymous classes or named inner classes
JButton myButton = new JButton("Click Me");
myButton.addActionListener(new ActionListener() { // unnamed inner class
		@Override
		public void actionPerformed(ActionEvent e) {
				// Action specific to this button
				System.out.println("Button clicked!");
		}
});
```

### Menu
Java provides several classes to implement menus: `JMenuBar`, `JMenu`, `JMenuItem`, `JCheckBoxMenuItem`, and `JRadioButtonMenuItem`.

**The `JMenuBar` Class** 
* Holds menus.
* Can only be added to a `JFrame`.
* **Example**:
    ```java
    JFrame f = new JFrame();
    f.setSize(300, 200);
    f.setVisible(true);
    JMenuBar mb = new JMenuBar();
    f.setJMenuBar(mb);
    ```

**The `JMenu` Class** 
* You attach menus onto a `JMenuBar`.
* **Example**:
    ```java
    JMenu fileMenu = new JMenu("File");
    JMenu helpMenu = new JMenu("Help");
    mb.add(fileMenu);
    mb.add(helpMenu);
    ```

**The `JMenuItem` Class** 
* You add menu items onto a `JMenu`.
* **Example**:
    ```java
    fileMenu.add(new JMenuItem("new"));
    fileMenu.add(new JMenuItem("open"));
    fileMenu.add(new JMenuItem("-")); // Separator
    fileMenu.add(new JMenuItem("print"));
    fileMenu.add(new JMenuItem("exit"));
    fileMenu.add(new JMenuItem("-")); // Separator
    ```

**Submenus** 
* You can add submenus within menu items.
* **Example**:
    ```java
    JMenu hardwareHelpSubMenu = new JMenu("Hardware");
    helpMenu.add(softwareHelpSubMenu); // softwareHelpSubMenu is defined 
    helpMenu.add(hardwareHelpSubMenu);
    softwareHelpSubMenu.add(new JMenuItem("Unix"));
    softwareHelpSubMenu.add(new JMenuItem("NT"));
    softwareHelpSubMenu.add(new JMenuItem("Win95"));
    ```



```
A JMenuBar can only be added to a JFrame using the setJMenuBar() method.
The ActionCommand string within an ActionEvent often identifies the source of the event, especially when multiple components share the same ActionListener.
Explanation: You add JMenu objects to a JMenuBar using the add() method of the JMenuBar.
Like JFrame, JDialog also uses setVisible(true) to make itself appear on screen.
java.awt.Component is the abstract superclass of the non-menu-related AWT components
JOptionPane.showInputDialog() returns a String representing the text entered by the user, or null if the user cancels.
You add JMenuItem objects to a JMenu using the add() method of the JMenu.
ButtonGroup logically groups JRadioButtons so that selecting one deselects the others.
The pack() method is convenient for sizing the frame automatically based on the size of its contents.
The ___JOptionPane ____ class provides static methods for creating standard dialog boxes.
BorderLayout is the default layout for top-level containers like JFrame and JDialog.
The default layout manager for a JPanel is FlowLayout.

The setJMenuBar(JMenuBar) method is specific to JFrame for setting its menu bar.

setEditable() for JTextField

Event listeners (not handlers) are responsible for 'listening' for and responding to specific events.

The GUI API classes in Java can be classified into three main groups: 
Containers- (e.g., JFrame, JPanel, JDialog).
Components - . (e.g., JButton, JLabel, JTextField).
Layout Managers  - (e.g., BorderLayout, FlowLayout, GridLayout).
DriverManager.getConnection("jdbc:mysql://localhost:3306/mydatabase", "username", "password");

DatagramPacket sendPacket = new DatagramPacket(sendData, sendData.length, clientAddress, clientPort);
DatagramPacket receivePacket = new DatagramPacket(receiveData, receiveData.length);
Thread-Pools: **Resource Management** – Avoids **thrashing** (excessive thread creation degrading performance).

Lock lock = new ReentrantLock();
Condition newDeposit = lock.newCondition();


Thread _Synchronization_ coordinates access to shared data by multiple concurrent threads.
What method of ExecutorService returns true if all tasks in the pool are terminated? _isTerminated()_
What is the consequence if the code between lock() and unlock() calls throws an exception? _unlock()_ is never called
Which method of the Lock interface is used to obtain a Condition object? newCondition()
The Thread.yield() method guarantees that other threads will execute immediately after it is called. False
When a Java thread's sleep() method is invoked, the thread becomes 'Not Runnable'. True
```























