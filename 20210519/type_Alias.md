# 타입 별칭(Type Alias)

# Aliasing Primitive

```ts
type MyStringType = string;
const str = 'world';

let myStr: MyStringType = 'hello';

myStr = str;
```
---
# Alising Union Type
### 1. 유니온 타입은 A도 가능하고 B도 가능한 타입
### 2. 길게 쓰는걸 짧게

```ts
let person: string | number = 0;
person = 'Mark';

type StringOrNumber = string | number;

let another: StringOrNumber = 0;
another = 'Anna'; 
```
---
# Aliasing Tuple 
### 1. 튜플 타입에 별칭을 줘서 여러군데서 사용할 수 있게 한다.

```ts
let person: [string, number] = ['Mark', 35];

type PersonTuple = [string, number];

let another: PersonTuple =['Anna', 24];
```
---
# Aliasing Function

```ts
type EatType = (food: string) => void;
```
