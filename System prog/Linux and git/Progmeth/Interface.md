[[Abstraction]]
- another way to achieve *abstraction* in java
- an **interface** is a completely "abstract class" that is used to group related methods with empty bodies.

#### Example
```java
interface Animal {
	// interface method does not have a body
	public void animalSound();
	public void sleep();
}
```

- To access the interface methods, the interface must be "implemented
- Must override all of its methods
- Interface attributes are by default `public`, `static` and `final`

```java
class Pig implements Animal {
	public void animalSound() {
		System.out.println("The pig says: wee wee");
	}	

	public void sleep() {
		System.out.println("ZZZ");
	}
}

class Main {
	public static void main(String[] args) {
		Pig myPig = new Pig();
		myPig.animalSound();
		myPig.sleep();
	}
}
```

**Why and When to use interface**
1. To achieve security - hide certain details and only show the important details of an object (interface).
2. Java does not support "multiple inheritance". However, it can be achieved with interfaces, because the class can *implement* multiple interfaces.

