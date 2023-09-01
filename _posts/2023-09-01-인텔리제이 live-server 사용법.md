---
layout: listings
date: 2023-09-01 10:15:33 +0900
---
* toc
{:toc}


# 개요

VS Code로 작업할 때 Live Server라는 플러그인을 사용해서 HTML 작업을 편하게 하는데

인텔리제이에서도 가능한지 알아보았는데 방법이 있어서 기록해둔다.

<img width="685" alt="image" src="https://user-images.githubusercontent.com/102304046/265036795-1a338bcb-d0c7-4d2e-b5da-00f9ddc88080.png">

# 방법

## 1. live-server 설치

```sh
npm install -g live-server
```

## 2. 작업 중인 프로젝트 폴더에서 live-server 실행

```sh
# 기본 실행 방법
# 127.0.0.1으로 접속된다.
live-server

# 파일명을 지정하는 방법
# 파일을 별도 지정을 안할 경우 index.html이 있으면 실행되지만 이렇게 지정할 수 있다.
live-server --entry-file=파일명.html
# 파일명 지정 방법 예시
live-server --entry-file=test.html

# 공유기 사용 접속법
# --host 옵션을 주고 테스트 PC의 ip를 입력하면 다른 디바이스에서도 접속이 가능하다.
live-server --host=ip주소
# 공유기 접속 예시
live-server --host=192.168.10.5
```
## 3. 실행결과
<img width="793" alt="image" src="https://user-images.githubusercontent.com/102304046/265037680-b6483c7b-7b3d-478f-b654-b124cadcc102.png">

# 참조

- [npm - live-server](https://www.npmjs.com/package/live-server)
  - 해당 사이트로 가면 다양한 옵션 사용방법이 있다.
- [vscode 버려! intellij에서 live-server쓰는방법](https://developer-kade.tistory.com/136)