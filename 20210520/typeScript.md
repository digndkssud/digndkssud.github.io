# TypeScript Compiler

---
# compileOnSave
## 저장하면 자동으로 컴파일을 해준다.

```plaintext
true / false (default false)
```

# extends

```plaintext
tsconfig.json과 비슷한 설정이 들어있는 부모설정의 경로
파일(상대) 경로명: string

```
```ts
// in PROJECT/base.json
{
  "compilerOptions":{
    "strict": true
  }
}

// in PROJECT/tsconfig.json
{
  "extends": "./base.json",
}
```

# filse, include, exclude

## 파일,디렉토리를 규정하는 property


```plaintext
- 셋다 설정이 없으면, 전부다 컴파일
- files
  - 상대 혹은 절대 경로의 리스트 배열
  - exclude 보다 강력
- include, exclude
  - glob 패턴(마치 .gitignore)

  - include
    - exclude 보다 약합니다.
    - * 같은걸 사용하면 .ts / .tsx / .d ts만 include(allowJS)
  - exclude
    - 설정 안하면 4가지(node_modules,bower_components, jspm_packages, <outDir>)를 default로 제외합니다.
    - <outDir>은 항상 제외합니다.(include에 있어도)
```


# compileOption - typeRoots, types

```plaintext
- TypeScript 2.0부터 사용 가능해진 내장 type definition 시스템
- 아무 설정을 안하면?
  - node_modules/@types 라는 모든 경로를 찾아서 사용
- typeRoots를 사용하면?
  - 배열 안에 들어있는 경로들 아래서만 가져옵니다.
- types를 사용하면?
  - 배열 안의 모듈 혹은./node_modules/@types/ 안의 모듈 이름에서 찾아옵니다.
  - [] 빈 배열을 넣는다는건 이 시스템을 이용하지 않겠다는 것입니다.
- typeRoots와 types를 같이 사용하지 않습니다.
```
