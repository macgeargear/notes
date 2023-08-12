- more than one form.
- same entity can perform different operations in different scenarios.

> We can achieve polymorphism in Java using the following ways:
> **1. Method Overriding
> 2. Method Overloading
> 3. Operator Overloading

#### Example
Example 1: Polymorphism using method overriding
```run-java
class Language {
	public void displayInfo() {
		System.out.println("Common English Langugage");
	}
}

class Java extends Language {
	@Override
	public void displayInfo() {
		System.out.println("Common English Langugage");
	}
}

class Main {
	public static void main(String[] args) {
		Java j1 = new Java();
		j1.displayInfo();

		Language l1 = new Language();
		l1.displayInfo();
	}
}
```

Example 2: Method Overloading
``` java
void func() {....}
void func(int a) {....}
float func(double a) {....}
float func(int a, float b) {....}
```

Example 3: Polymorphism using method overloading
``` java
display() {....}
display(char symbol) {...}
```

