# 2021-04-27 Markdown 작성방법

---

# 제목(Header)

```plaintext
# 제목1
## 제목2
### 제목3
#### 제목4
##### 제목5
###### 제목6
```
# =>

# 제목1
## 제목2
### 제목3
#### 제목4
##### 제목5
###### 제목6
---

# 문장(paragraph)


동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세

---

# 줄바꿈(Line Breaks - 스페이스바 두번 넣기)


동해물과 백수단이 마르고 닳도록  
하느님이 보우하사 우리나라 만세  
무궁화 삼천리 화려 강산  
대한 사람 대한으로 길이 보전하세

---

# 강조(Emphasis)
```plaintext
_이텔릭_  
**두껍게**
**_이텔릭 + 두껍게_**  
~~취소선~~
<u>밑줄</u>
```
# =>
_이텔릭_  
**두껍게**
**_이텔릭 + 두껍게_**  
~~취소선~~  
<u>밑줄</u>

```plaintext
1. 순서가 필요한 목록
1. 순서가 필요한 목록
    1. 순서가 필요한 목록
    1. 순서가 필요한 목록
1. 순서가 필요한 목록
1. 순서가 필요한 목록

- 순서가 필요하지 않은 목록
- 순서가 필요하지 않은 목록
- 순서가 필요하지 않은 목록
    - 순서가 필요하지 않은 목록
    - 순서가 필요하지 않은 목록

- 순서가 필요하지 않은 목록
```
# =>
1. 순서가 필요한 목록
1. 순서가 필요한 목록
    1. 순서가 필요한 목록
    1. 순서가 필요한 목록
1. 순서가 필요한 목록
1. 순서가 필요한 목록

- 순서가 필요하지 않은 목록
- 순서가 필요하지 않은 목록
- 순서가 필요하지 않은 목록
    - 순서가 필요하지 않은 목록
    - 순서가 필요하지 않은 목록

- 순서가 필요하지 않은 목록
---

# 링크(Links)

```paintext

<a href="https://google.com">GOOGLE<a/>

[GOOGLE](https://google.com)

[NAVER](https://naver.com "NAVER로 이동!")

<a href="https://naver.com" title="NAVER로 이동!" target="_blank">NAVER</a>

```
# =>

<a href="https://google.com">GOOGLE<a/>

[GOOGLE](https://google.com)

[NAVER](https://naver.com "NAVER로 이동!")

<a href="https://naver.com" title="NAVER로 이동!" target="_blank">NAVER</a>

---

# 이미지(Image)

![image](https://user-images.githubusercontent.com/61581807/116191963-268acc80-a768-11eb-82ca-e5b2230d83fd.png)

---

# 인용문(BlockQuote - 꺽새를 닫고 시작)

```plaintext
> 남의 말이나 글에서 직접 또는 간접으로 따온 문장.  
> (네이버 국어 사전)
```
# =>
> 남의 말이나 글에서 직접 또는 간접으로 따온 문장.  
> (네이버 국어 사전)

---

# 인라인(inline) 코드 강조(강조하고 싶은 곳에 grave 입력)

```plaintext
CSS에서 `background` 혹은 `background-image` 속성으로 요소에 배경 이미지를 삽입할 수 있습니다.
(``으로 표현)
```
=> CSS에서 `background` 혹은 `background-image` 속성으로 요소에 배경 이미지를 삽입할 수 있습니다.

---

# 블록(block) 코드 강조


![image](https://user-images.githubusercontent.com/61581807/116193880-ff81ca00-a76a-11eb-90b3-0a0aac2be2c3.png)

---

# 표(Table)

기본 정렬 값은 왼쪽 정렬
콜론(:)을 통해 조작 가능


```plaintext
position 속성   

값 | 의미 | 기본값
--|:--:|--:
static | 기준 없음 | o
relative | 요소 자신 | X
absolute | 위치 상 부모 요소 | X
fixed | 뷰포트 | X
```
# =>
값 | 의미 | 기본값
--|:--:|--:
static | 기준 없음 | o
relative | 요소 자신 | X
absolute | 위치 상 부모 요소 | X
fixed | 뷰포트 | X



---

# 원시 HTML(Raw HTML)

![image](https://user-images.githubusercontent.com/61581807/116198012-65248500-a770-11eb-9371-03e8555ffea9.png)

---

# 수평선(Horizontal Rule)

```plantext
---

***

___

```
# =>
---

***

___

