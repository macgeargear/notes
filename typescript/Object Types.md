the object type in typescript can be named by using `interface` or `type` alias
- interface
```ts
interface Person {
	name: string;
	age: number;
}
function greet(person: Person) {
	return "Hello " + person.name;
}
```
- type alias
```ts
type Person = {
	name: string;
	age: number;
};
function greet(person: Person) {
	return "Hello " + person.name;
}
```


### Property Modifiers
- Optional Properties: ?
- `readonly` Properties
	- can't be change any behavior at runtime
 ```ts
interface SomeType {
	readonly prop: string;
}
function doSomething(obj: SomeType) {
console.log(`prop has the value '${obj.prop}'.`);
obj.prop = "hello"; // error
}
```
> Cannot assign to 'prop' because it is a read-only property.Cannot assign to 'prop' because it is a read-only property.

### Index Signatures
Sometimes you don’t know all the names of a type’s properties ahead of time, but you do know the shape of the values.
> `string`, `number`, `symbol` are allowed for index signatures
```ts
interface StringArray {
	[index: number]: string;
}
const myArray: StringArray = getStringArray();
const secondItem = myArray[1];
```

> Q: It is possible to support both types of indexers...

Ans: Possible but, the type returned from a numeric indexer must be a subtype of the type returned from the string indexer

- Properties of different types are acceptable if the index signature is union of the property types
```ts
interface NumberOrStringDictionary {
	[index: string]: number | string;
	length: number;
	name: string;
}
```

