# 변수 유효범위(Variable Scope)
## var, let, const

```javascript
function scope() {
  if (true) {
    const a = 123
    console.log(a)
  }
}
scope()


```

#  형 변환(Type conversion)
## Truthy(참 값은 값)
### true, {}, [], 1, 2, 'false', -12, '3.14' ... 
## Falsy(거짓 같은 값)
### false, '', null, undefined, 0, -0, NaN

```javascript
if(true){
  console.log(123) 
}

```