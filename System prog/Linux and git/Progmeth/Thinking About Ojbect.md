[[Encapsulation]]
[[Inheritance]]
[[Abstraction]]
[[System prog/Linux and git/Progmeth/Interface]]

![[Screenshot 2023-02-09 at 9.21.53 PM.png]]
![[Screenshot 2023-02-09 at 9.23.50 PM.png]]
##### Step 1: constructor
``` java
public class Elevator {
	public Elevator() {}
}
```

##### Step 2: attributes
```java
public class Elevator {
	// attrs
	private boolean moving;
	private boolean summoned;
	private int currentFloor = 1;
	private int destinationFloor = 2;
	private int capacity = 1;
	private int travelTime = 5; 

	// constructor
	public Elevator() {}
}

```

##### Step 3: associated objects
```java
public class Elevator {
	// attrs
	private boolean moving;
	private boolean summoned;
	private int currentFloor = 1;
	private int destinationFloor = 2;
	private int capacity = 1;
	private int travelTime = 5; 

	// associated objects
	private ElevatorDoor elevatorDoor;
	private ElevatorButton elevatorButton;
	private Bell bell;

	// constructor
	public Elevator() {}
}

```

##### Step 4: Operations
```java
public class Elevator {
	// attrs
	private boolean moving;
	private boolean summoned;
	private int currentFloor = 1;
	private int destinationFloor = 2;
	private int capacity = 1;
	private int travelTime = 5; 

	// associated objects
	private ElevatorDoor elevatorDoor;
	private ElevatorButton elevatorButton;
	private Bell bell;

	// constructor
	public Elevator() {}

	// operations
	public void ride() {}
	public void requestElevator() {}
	public void enterElevator() {}
	public void exitElevator() {}
	public void departElevator() {}
}

```
