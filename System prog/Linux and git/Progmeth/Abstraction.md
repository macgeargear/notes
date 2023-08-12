[[Inheritance]]
[[System prog/Linux and git/Progmeth/Interface]]
### Advance Concepts
- Abstract class 
- Dynamic binding
	- Create a single method that has >= 1 params that might be one of several types
	- Create a array of superclass but store multiple subclss instance in it
 
##### Abstract Classes
- Abstract Classes cannot be instantiated. 
- base for superclass

``` java 
public abstract class MyAbstract { ... }
MyAbstractClass myClassInstance = new MyAbstractClass(); // NOT VALID
```

- can have abstract method (template)
	- abstract method *no implementation* just method signature.
	- *Subclass* of abstract class **must implement (override) all abstract methods** of its abstract superclass
 ``` run-java
public abstract class MyAbstract {
	public abstract void abstractMethod();
}
```

```run-java
public class MySubClass extends MyAbstractClass {
	public void abstractMethod() {
		System.out.println("My method implementation");
	}
}
```

- Abstract method does *not* have
	- Body
	- Curly braces
	- Method statements
 - To create abstract method: **method type, name, arguments**
``` java
// method type, name, arguments
public abstract void speak();
```
- Subclass of abstract class
	- **Inherits abstract method** from parent
		- Must provide implementation for inherited method
		- Or be abstract itself
	 - Code subclass method to override empty superclass method

### Using Dynamic Method Binding





### Using a Sperclass as a Method Parameter Type (method argument)
``` run-java
public class TalkingAnimalDemo {
	public static void main(String[] args) {
		Dog dog = new Dog();
		Cow cow = new Cow();
		dog.setName("Ginger");
		cow.setName("Molly");
		talkingAnimal(dog);
		talkingAnimal(cow);
	}

	public static void talkingAnimal(Animal animal) {
		System.out.println("Come one. Come all.");
		System.out.println("See the amazing talking animal!");
		System.out.println(animal.getName() + " says");
		animal.speak();
	}
}

class Animal {
	String name;
	public String getName() {
		return this.name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public void speak() {
		 System.out.println("Animal say!!");
	}
}

class Dog extends Animal {
	public void speak() {
		System.out.println("Bruwwwww");
	}
}

class Cow extends Animal {
	public void speak() {
		System.out.println("MOOOOOOOOO");
	}
}

```

#### Creating Arrays of Subclass Objects
- Create superclass refernce
	- Treat subclass objects as superclass objects
		- Create array of different objects
		- Share same ancestry
- Creates array of three `Animal` references
	> `Animal[] ref = new Animal[3];` Reserve memory for three `Animal` object references

##### Using the **object** class
- Every Java class extension of `Object` class
- Defined in `java.lang` package
- imported automatically
- Includes methods to use or override

### Method summary
``` java
clone()
equals(Object obj)
hashcode()
finalize()
toString()
getClass()

// Cannot override
notify()
notifyAll()
wait(); wait(long timeout);
wait(long timeout, int nanos);
```

#### The equals() method
> reflextive
> symmetric
> transitive
> consistent
   non-null

- Compares this object to the specified object.
- return `true` if 
	- argument != null 
	- String object that represents the same sequence of characters as this object.
 ```java example.java
// equals method example
public class Employee {
	int employeeId;
	String firstName, lastName;
	public boolean equals(Object o) {
		if (this == o) return true;
		if (o == null) return false;
		if (o.getClass() != this.getClass()) return false;

		Employee other = (Employee) o;
		if (this.employeeId != other.employeeId ) return false;
		if (!this.firstName.equals(other.firstName)) return false;
		if (!this.lastName.equals(other.lastName)) return false;
		return true;
	}
}
```

#### The clone() method
- To create an object from an existing object
> Must Implement **Clonable**
> x.clone() != =
> x.clone().getClass() == x.getClass()
> x.clone().equals(x)

##### Clone example
``` java
// clone example
public class Stack implements Cloneable {
	private Vector items;
	// constructor, method ...
	protected Object clone() {
		try {
			Stack s = (Stack) super.clone(); // Clone the stack
			s.items = (Vector) items.clone(); // Clone the vector
			return s;
		} catch (CloneNotSupportedException e) {
			// this should not be happen	
			throw new InteralError();
		}
	}
}
```

``` java
// clone example 2
Class A {
	private int x;
	public A(int i) {
		x = i;
	}
}

public class CloneDemo1 {
	public static void main(String[] args) throws CloneNotSupportedException {
		 A obj1 = new A(37);
		 A obj2 = (A) obj1.clone(); 
		// ^ this will cause compile error because Object.clone() is a protected method.
	}
}
```

```java
Class A {
	private int x;
	public A(int i) {
		x = i;
	}
	public Object clone() {
		try {
			return super.clone();
		}
		catch (CloneNotSupportedException e) {
			throw new InternalError(e.toString());
		}
	}
}

// CloneDemo2.java
public class CloneDemo2 {
	public static void main(String[] args) throws CloneNotSupportedException {
		A obj1 = new A(37);
		A obj2 = (A) obj1.clone(); // Exception is thrown at runtime;	
	}
}
```

```java
Class A implements Cloneable {
	private int x;
	public A(int i) {
		x = i;
	}
	public Object clone() {
		try {
			return super.clone();
		}
		catch (CloneNotSupportedException e) {
			throw new InternalError(e.toString());
		}
	}
	public int getX() return this.x;
}

// CloneDemo3.java
public class CloneDemo3 {
	public static void main(String[] args) throws CloneNotSupportedException {
		A obj1 = new A(37);
		A obj2 = (A) obj1.clone(); // Exception is thrown at runtime;	
		System.out.println(obj2.getX());
	}
}
```

#### There are other ways **better than clone()**
1. Copy constructor
2. Static factory
```java
class A4 implements Cloneable {
	private int x;
	public A4(int i) {
		this.x = i;
	}
	// 1. copy constructor
	public A4(A4 other) {
		this.x = other.getX();
	}

	// 2. static factory
	public static A4 newInstatce(A4 other) {
		A4 obj = new A4(other.getX());
		return obj;
	}

	// getter
	public int getX() return this.x;
}
```

``` java
public class CloneDemo4 {
	public static void main(String[] args) {
		A4 obj1 = new A4(37);
		A4 obj2 = new A4(obj1);
		System.out.println(obj2.getX());

		A4 = obj3 = A4.newInstance(obj1);
		System.out.println(obj2.getX());
	}
}
```

#### The finalize() method !!!!!!! Deprecated !!!!!!!!!
- Before an object is **garbage collected** the run time system calls ints finalize() method.
- to release system resources
- **Usage**
	- Always `call super.finalize()` in `finalize()` method
	- do not put time critital application logic in `finalze()`
	- do not use `Runtime.runFinalizersOnExit(true)` as it can put your system in danger