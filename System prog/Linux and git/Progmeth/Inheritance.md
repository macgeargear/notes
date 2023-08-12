## Implementation
- keyword `extends` 
	- Achieve inheritance in Java
	- Can extends from only **one** superclass
- Inheritance one-way proposition
	- Child inherits from parent, not the other way round.


#### Case Study: Student
![[Student.canvas]]
``` java
// Student.java
public class Student {
	protected final static int NUM_OF_TEST = 3;
	protected String name;
	protected int[] test;
	protected String courseGrade;
}
```

``` java
// UndergraduateStudent.java 
public class UndergraduateStudent extends Student {
	public UndergraduateStudent(String studentName) {
		super(studentName);
	}
	public void computeCourseGrade() {
		// calculation 1
	}
}
```

``` java
public class GraduateStudent extends Student {
	String advisorName;
	public void computeCourseGrade() {
		// calculation 2
	}
}
```

##### **Save time & Reduce errors**
- [?] Is ther anything wrong in the following code?
	- If yes, should the issue also happen in Student's subclasses?
	- How many method should we fix the issue?
 ``` java
// Student.java (with ArrayIndexOutOfBound)
public int getTestScore(int testNumber) {
	return test[testNumber - 1];
}
```

``` java
// Student.java (no error)
public int getTestScore(int testNumber) {
	return (testNumber <= NUM_OF_TESTS) ? test[testNumber - 1] : test[0];
}
```


## Overriding Superclass Methods
 **Cerate subclass by extending existing class**
 - Subclass contains data and methods defined in original superclass
 - Sometimes superclass data fields and methods not entirely appropriate for subclass objects
 **Polymorphism (in general)**
 - Override method in parent class
 - Subtype polymorphism
### Override method in parent class
- Must have same signature

##### ex1
``` java
// Student.java
class Student {
	public void printName() {
		System.out.println("Student[ "+name+" ]")
	}
}
```

``` java
// GraduateStudent.java
class GraduateStudent extends Student {
	public void printName() {
		System.out.println("GraduateStudent[ "+name+" ]")
	}
}
```
##### ex2

``` java
 public class StudentTest1 {
	public static void main(String[] args) {
		Student s1 = new UndergraduateStudent("Toey"); Student s2 = new GraduateStudent("Nat"); 
		Student s3 = new Student("Jump");
		s1.printName(); 
		s2.printName(); 
		s3.printName();
} }
```
**Result**
```
UndergraduateStudent [Toey]
GraduateStudent [Nat]
Student [Jump]
```

## Subtype polymorphism

``` java
//StudentTest2.java
public class StudentTest2 {
	public static void main(String[] agrs) {
		 Student s1 = new UndergraduateStuden("Toey");	
		 StudentTest2.checkStatus(s1);
	}

	public static void checkStatus(Student s) {
		if (s instanceof UndergraduateStudent) {
			System.out.println("You are UndergraduateStudent");
		}
	} 

}
```

## Up/Down casting
- upcasting (automatically)
``` java
Student s1 = new GraduateStudent("nat");
s1.printName();
```
- downcasting (manually) - **may have problem**
	this code will cause error because *cannot downcasting parant class to child class*
```java
Student s = new Student("Luch");
UndergraduateStudent s2 = (UndergraduateStudent) s;
```
 
## Keyword 'super'
- `super` is a ref variable refering to **parent class object**
- when create instance of subclass, an instance of parent class is created implicity (only for non-argument constructor)
- Usage of keyword **'super'**
	- refer to **parent class instance variable**
	- invoke **parent class constuctor**
	- invoke **parent class method**

### Instance Creation Mechanism
``` java
public class ClassCreation {
	public static void main(String[] args) {
		C c1 = new C(5);
	}
}

class A {
	A() {
		System.out.println("class A");
	}
}

class B extends A {
	B(int val) {
		// super();
		System.out.println("class B, value" + val);
	}
}

class C extends B {
	C(int val) {
		super(val);
		System.out.println("class C, value=" + val)
	}
}
```
- When superclass contains default constructor
	- Execution of superclass constructor transparent
	- C -> B -> A
 - using superclass constructors that require arguments
	 - when superclass has default contructor
		 - can create subclass with or without own constructor (auto)
	 - when there is **no** default constructor in superclass
		 - Must include at least one for subclass
		 - First State ment within constructor must call `super`

##### Method you Cannot Override
- **Static** methods
- **final** methods
- Methods within **final** classes (can't be extended)

### Subclass can't Override static methods


## Dynamic method binding






---
- [?] What is the output ?
``` java
public class A {
	public static void main(String[] args) {
		A a = new B();
		a.foo();
	}

	private void foo() {
		System.out.println("A");
	}
}

class B extends A {
	public void foo() {
		System.out.println("B");
	}
}
```