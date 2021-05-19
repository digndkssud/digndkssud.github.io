# structural type system 
## 구조가 같으면, 같은 타입이다.

```ts
interface IPerson {
  name: string;
  age: number;
  speak(): string;
}

type PersonType = {
  name: string;
  age: number;
  speak(): string;
}

let personInterface: Iperson = {} as any;
let personType: PersonType = {} as any;

personInterface = personType;
personType = personInterface;

```

# nominal type system 
## 구조가 같아도 이름이 다르면, 다른 타입이다.

```ts
type PersonID =string & { readonly brand: unique symbol };

function PersonID(id: string): PersonID {
  return id as PersonID;
}

function getPersonById(id: PersonID) {}

getPersonById(PersonId('id-aaaaaa'));
getPersonById('id-aaaaaa'); // error

```
