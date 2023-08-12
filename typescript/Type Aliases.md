```typescript
type Point = {
  x: number;
  y: number;
};

function printCoord(pt: Point) {
  console.log(pt.x + pt.y);
}
```

a type alias can name a union type:
```typescript
type ID = number | string
```

you can not use type aliases to create diffent/distinct "versinos" of the same type
```typescript
type UserInputSanitizedString = string

function sanitizeInput(str: string): UserInputSanitizedString {
	return sanitize(str);
} 

// Create a sanitized input
let userInput = sanitizeInput(getInput());

// Can still be re-assigned with a string though
userInput = "new input"
```


