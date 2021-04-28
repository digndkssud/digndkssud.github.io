# 유의적 버전(SemVer)  

```plaintext
Major.Minor.Patch

12.14.1

Major = 기존 버전과 호환되지 않는 새로운 버전
Minor = 기존 버전과 호환되는 새로운 기능이 추가된 버전
Patch = 기존 버전과 호환되는 버그 및 오타 등이 수정된 버전.

```

```bash
$ npm install lodash@4.17.20
//설치하고자 하는 패키지 + @ + 버전 (주로 다운그레이드 할 때 사용)

$ npm update lodash
// 해당 패키지를 업데이트한다
// 만약 '^(캐럿)' 표시가 없으면 업데이트 안 함.

```
