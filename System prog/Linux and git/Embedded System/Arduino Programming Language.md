```c++
#define LED_PIN 13
void setup() {
	pinMode(LED_PIN, OUTPUT);
}

void loop() {
	// Turn on the LED
	digitalWrite(LED_PIN, HIGH);
	// Wait 1 sec
	delay(1000)
	// Turn of the LED
	digitalWrite(LED_PIN, LOW);
	// Wait 1 second
	delay(1000);
}
```

#### Arduio Math Constants
-   `M_PI` the constant pi (`3.14159265358979323846`)
-   `M_E` the constant e
-   `M_LN10` the natural logarithm of the number 10.
-   `M_LN2` the natural logarithm of the number 2.
-   `M_LOG10E` the logarithm of the e to base 10.
-   `M_LOG2E` the logarithm of the e to base 2.
-   `M_SQRT2` the square root of 2.
-   `NAN` the NAN (not a number) constant.

#### Built-in Functions
-  `setup()` this function is called once, whenthe program starts, and when it shut down and restarted.
- `loop()` repeatedly called while the Arduino program is running

### Handling IO
#### Ditigal I/O
- `digitalRead()`
- `digitalRead()`
- `pinMode()`: setup a pin to be an input, or an output
- `pulseIn()`:
#### Analog I/O

#### Time Function
#### Math functions
#### Working with alphanumeric characters
#### Random numbers generation
#### Working with bits and bytes
#### Interrupts
