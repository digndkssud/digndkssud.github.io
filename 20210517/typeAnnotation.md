# Annotation


npx tsc
node test.js


```ts
let a: string

a = "Mark"

a = 39 // error

function hello(b: number){

}

hello(39)
hello('Mark') // error
```

# Primitive Type

## boolean
```ts
let isDone: boolean = false;

isDone =true;

console.log(typeof isDone) // 'boolean'


let isOk: Boolean = true

let isNotOk: boolean = new Boolean(true)
```

## number

```ts
let decimal: number = 6 // 10진수 리터럴

let hex: number = 0xf00d // 16진수 리터럴

let binary: number =0b1010 // 2진수 리터럴

let octal: number = 0o744; // 8진수 리터럴

let notANumber: number = NaN

let underscoreNum: number = 1_000_000
```

## string

```ts
let myName: string = "Mark";

myName = 'Anna';

// Template String

let fullName: string = 'Mark Lee';

let age: number = 39;

let sentence: string = `Hello, my name is ${ fullName }.

I'll be ${age + 1} years old next month.`;

console.log(sentence)
```

## symbol

### 고유하고 수정불가능한 값으로 만들어준다.

```ts
console.log(Symbol('foo') === Symbol('foo')); // false

const sym = Symbol();

const obj = {
  [sym]: "vlaue",
};
   
console.log(obj[sym])// "value"
```

## Undefined & Null

```ts
// let MyName: number =undefined;
// let u: undefined = null;

let v:void =undefined; //undefined만 가능

let union: string | null = null;

union = "Mark";
```

## object

```ts
// create by object literal
const personal ={name: 'Mark', age: 39};

// personal is not "object" type.
// personal is "{name: string, age: number}" type.

// create by Object.create

const person2 = Object.create({name: 'Mark', age: 39});


let obj: object = {};

obj = {name: 'Mark'};

obj = [{name: 'Mark'}];

obj = 39; // Error

obj = 'Mark'; // Error

obj = true // Error

obj = 100n// Error

obj = Symbol();// Error

obj = null; // Error

obj = undefined; // Error

declare function create(o: object | null): void;

create({ prop: 0});

create(null);

create(42); // Error

create("string")// Error

create(false)// Error

create(undefined)// Error

// Object.create
Object.create(0); // Error

```
