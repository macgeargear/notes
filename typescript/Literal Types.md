By themself, literal types aren't very valuable
```ts
let x: "hello" = "hello";  // OK  
x = "hello";  
// ...  
x = "howdy";  
```
> Type '"howdy"' is not assignable to type '"hello"'.

- It’s not much use to have a variable that can only have one value!
- But by _combining_ literals into unions, you can express a much more useful concept - for example, functions that only accept a certain set of known values:
```ts
function printText(s: string, alignment: "left" | "right" | "center") {
	// ...
}

printText("Hello, world", "left")
printText("Hello, world", "center") // error
```
>Argument of type '"centre"' is not assignable to parameter of type '"left" | "right" | "center"'.

Numeric literal types work the same way:
```ts
function compare(a: string, b: string): -1 | 0 | 1 {
	return a == b ? 0 : a > b ? 1 : -1
}
```

Of course, you can combine these with non-literal types:
```ts
interface Options {
	width: number;
}

function configure(x: Options | "auto") {
	// ...
}

configure({width: 100})
configure("auto")
configure("automatic") // error
```
>Argument of type '"automatic"' is not assignable to parameter of type 'Options | "auto"'.

There’s one more kind of literal type: boolean literals. There are only two boolean literal types, and as you might guess, they are the types `true` and `false`. The type `boolean` itself is actually just an alias for the union `true | false`.

There’s one more kind of literal type: boolean literals. There are only two boolean literal types, and as you might guess, they are the types `true` and `false`. The type `boolean` itself is actually just an alias for the union `true | false`.

**Literal Inference**
---
When you initialize a variable with an object, TypeScript assumes that the properties of that object might change values later. For example, if you wrote code like this:
```ts
const obj = { counter: 0 };  if (someCondition) {  obj.counter = 1;  } 
```

TypeScript doesn’t assume the assignment of `1` to a field which previously had `0` is an error. Another way of saying this is that `obj.counter` must have the type `number`, not `0`, because types are used to determine both _reading_ and _writing_ behavior.


