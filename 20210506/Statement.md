# 문법(조건문, 반복문)



# getRandom(숫자를 무작위로 생성해주는 함수)


```javascript
getRandom.js //에서

export default function random(){
  return Math.floor(Math.random()*10) // floor는 소수점 자리 내림/버림
}

main.js //에서

import random from './getRandom'

# 조건문 (If statement)

console.log(random()) 

const a = random()

if( a === 0 ){
  console.log('a is 0')
} else if( a === 2 ){
  console.log('a is 2')
}else if( a === 4 ){
  console.log('a is 4')
} else {
  console.log('rest ...')
}
```

# 조건문 (Switch statement)

```javascript
switch (a){
  case 0:
    console.log('a is 0')
    break // **** 꼭 break로 마무리 해줄 것!
  case 1:
    console.log('a is 1')
    break
  case 2:
    console.log('a is 2')
    break
  case 3:
    console.log('a is 3')
    break
  case 4:
    console.log('a is 4')
    break
  default : // 나머지일 경우에만
    console.log('rest...')
}

```

# 반복문 (For statement)
## for (시작조건; 종료조건; 변화조건){}

```javascript

const ulEl = document.querySelector('ul')

for(let i = 0; i < 3 ; i += 1){
  const li = document.createElement('li')
  li.textContent = `list-${i + 1}` // li의 텍스트를 설정한다.
  if((i + 1)% 2 === 0 ){
    li.addEventListener('click', function(){
      console.log(li.textContent)
    })
  }
  ulEl.appendChild(li) //li를 추가한다.
}
```
