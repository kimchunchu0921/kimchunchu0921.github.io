---
title: Open AI Chatgpt Apps SDK Pizzaz 예제 설치
description: Apps sdk 예제인 Pizzaz 앱을 chatgpt에 설치해보고 실행해보기
author: kimchunchu0921
date: 2025-10-15 11:03:00 +0900
categories: [Blogging, Develop]
math: true
mermaid: true
tags: [openai, ai, appssdk, pizzaz, chatgpt]
---

Open AI의 Apps SDK 예제를 직접 해봤습니다.

아직은 ChatGPT 유료 플랜만 가능한 것 같아요.

ChatGPT 개발자모드를 이용해야 하는데, 무료 플랜에서는 불가하더군요.

<br/>

1. 먼저 OpenAI에서 공개한 [오픈소스](https://github.com/openai/openai-apps-sdk-examples)를 클론합니다. 
```shell
git clone https://github.com/openai/openai-apps-sdk-examples.git
cd openai-apps-sdk-examples
```
<br/>
2. node.js v18이상이나, python 3.10이 필요하다고 합니다. 저는 node.js를 사용해서 진행했습니다.<br/><br/>
nvm으로 node.js 버전을 관리하고 있어서 아래 명령어를 실행해주었습니다.<br/>
그리고 pnpm도 필요해서 pnpm도 설치해주었습니다.
```shell
nvm use 22
npm install -g pnpm
```
<br/>
3. 의존성 모듈을 설치하고, 빌드도 해줍니다.<br/>
```shell
pnpm install
pnpm run build
```
<br/>
4. pizzaz 서버를 실행합니다.
```shell
cd pizzaz_server_node
pnpm start
```
<br/>
5. 서버를 실행한 쉘 말고, 다른 쉘에서 ngrok도 실행해줍니다.
```shell
ngrok http 8000
```
<br/>
6. 이제 준비는 되었습니다.<br/>
chatgpt에 접속하셔서 왼쪽 아래 계정을 클릭하셔서, `설정` > `Apps & Connectors` 에 들어갑니다.
![설정](/assets/img/post/2025-10/43.png){: .w-50 }
![AppsConnectors](/assets/img/post/2025-10/44.png){: .w-50 }
<br/>
<br/>
7. `Apps & Connectors` 오른쪽 위에 만들기 버튼을 클릭해줍니다.
![만들기](/assets/img/post/2025-10/45.png){: .w-50 }
<br/>
아이콘은 저는 생략했습니다.<br/>
이름은 `pizzaz`로 했구요.<br/>
설명도 생략했고,<br/>
MCP 서버 URL은 아까 `ngrok http 8000`을 실행했을 때 생성된 url 뒤에 `/mcp`를 붙여서 넣어주시면 됩니다.<br/>
`https://<ngrok-subdomain>.ngrok.app/mcp` 이런 식이죠.<br/>
저는 처음에 뒤에 `/mcp`를 안 붙이고 했더니, 자꾸 오류가 났습니다.<br/>
<br/>
인증은 `인증 없음`으로 설정하고, 체크박스 체크한 뒤에 만들면 됩니다.<br/><br/>
8. 그럼 아래와 같이 Connectors에 `Pizzaz` 가 추가됩니다.<br/>
![만들기](/assets/img/post/2025-10/46.png){: .w-50 }
<br/>
<br/>
9. 이제 gpt 채팅에서 `+`버튼 > `더보기` > `pizzaz` 선택하시면 gpt에서 pizzaz를 불러올 수 있습니다. <br/>
![만들기](/assets/img/post/2025-10/48.png){: .w-50 }
<br/>
<br/>
10. 채팅을 해보니 `pizzaz` 앱을 잘 불러오네요.<br/>
![만들기](/assets/img/post/2025-10/47.png){: .w-50 }



<br/>
이상, OpenAI Apps sdk 예제를 실행해보는 포스팅을 마치겠습니다. <br/> 
읽어주셔서 감사드립니다. 좋은 하루 보내시기 바랍니다.
