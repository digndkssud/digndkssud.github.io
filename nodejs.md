# 2021-04-27(nodejs, NVM 설치)

가급적이면 [공식홈페이지](https://nodejs.org/ko/)에서 LTS 다운로드 받는 것이 좋다.


![image](https://user-images.githubusercontent.com/61581807/116206453-c735b800-a779-11eb-905e-5870a4121543.png)

---

더욱 전문적으로 프론트 엔드를 개발하고 싶으면 [NVM(Node Version Manager)](https://github.com/coreybutler/nvm-windows/releases) 설치!

![image](https://user-images.githubusercontent.com/61581807/116206360-ab321680-a779-11eb-9c3d-668cf8925390.png)

---

```bash

$ nvm ls   // 설치되어 있는 nodejs 리스트

$ nvm install 12.14.1 // 다운로드 받고 싶은 버전을 설치

$ nvm use 12.14.1 // 사용할 nodejs의 버전을 선택

$ nvm uninstall 12.21.0 // 해당 버전의 nodejs를 삭제

$ node // 위의 과정을 거치면 해당 명령어를 사용할 수 있게 된다.

```


