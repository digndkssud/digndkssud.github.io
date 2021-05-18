# Array

## Array<타입>
```ts
let list: Array<number> = [1, 2, 3];
```
## 타입[ ] 
### 이 케이스를 자주 사용
```ts
let list: number[] = [1, 2, 3];
// 같은 속성들만 배열로 만들 수만 있다.
let list: (number | string)[] = [1, 2, 3, "4"];
// union을 사용해 다른 속성도 포함 가능
```
---

# Tuple

```ts
let x: [string, number];

x = ["hello",39];

x = [10, "Mark"];// error

x[3] = "world"; // error

const person: [string, number] = ["mark", 39];

const [first, second, third] = person; // error
// 분해할당

```

---
# Any
### 어떤 타입이어도 상관없는 타입
```ts
function returnAny(message): any {
  console.log(message);
}

const any1 = returnAny("리턴은 아무거나");

any1.toString();


let looselyTyped: any = {};
const d = looselyTyped.a.b.c.d;

function leakingAny(obj : any){
  const a: number = obj.num;
  const b = a + 1;
  return b;
}

const c = leakingAny({ num:0 });
// c.indexOf("0");
```
---

# Unknown 

### any와 짝으로 any 보다 Type-safe한 타입

```ts
declare const maybe: unknown;

const aNumber: number = maybe; // error

if (maybe === true){
  const aBoolean: boolean = maybe;
  
  const aString: string = maybe;// error
}

if(typeof maybe === 'string'){
  const aString: string = maybe;
  
  const aBoolean: boolean = maybe;// error
}
```
---
# Never
### 모든 타입의 subtype, 모든 타입에 할당 할 수 있다.
### 하지만 never에는 그 어떤 것도 할당할 수 없다.
### 잘못된 타입을 넣는 실수를 막고자 할 때 사용
```ts
function error(message: string): never {
  throw new Error(message);
}

function fail(){
  return error('failed');
}

function infiniteLoop(): never{
  while(true){}
}

declare const a: string | number;

if(typeof a !== 'string'){
  a;
}

type Indexable<T> = T extends string ? T & {[ index : string]: any} : never;
// 삼항 연산자

type ObjectIndexable = Indexable<'d'>
// type ObjectIndexable = Indexable<{}>// never

```
---
# Void

### undefined를 return하거나
### return을 사용하지 않을 때   


```ts
function returnVoid(message: string): void{
  console.log(message);

  return undefined;
}

returnVoid('리턴이 없다.');
// r은 void
```