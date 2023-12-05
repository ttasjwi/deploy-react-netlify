# Vercel에 React 프로젝트 배포해보기

---

## 개발 환경(Ubuntu)
### Node.js, npm
```shell
# apt 명령을 통해 nodejs, npm 설치
sudo apt install nodejs
sudo apt install npm


# 버전 확인 : 옛날 버전이 받아짐 
node -v      
v12.22.9
 
npm -v
8.5.1

# n 을 npm에 글로벌 추가 후, lst 버전으로 node 버전 변경
sudo npm install -g n
sudo n lts

$ node -v   
v20.10.0
 
$ npm -v
10.2.3
```

### yarn
```shell
# yarn 설치(https://yarnpkg.com/getting-started/install)
sudo corepack enable

# yarn 업데이트
corepack prepare yarn@stable --activate
```

---

## 리액트 프로젝트 생성(Create React App)
```shell
## create-react-app 으로 프로젝트 생성
yarn create react-app deploy-react-netlify

## 최신 yarn 버전과 create-react-app의 eslint 충돌 해결
yarn add eslint eslint-config-react-app --dev
```

---

## `.gitignore` 처리
<a href="https://yarnpkg.com/getting-started/qa#which-files-should-be-gitignored" target="_blank">yarn에서 공식적으로 제공하는 솔루션</a>
### 방법1: yarn의 zero install 을 사용할 경우
```gitignore
.yarn/*
!.yarn/cache
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions
```
### 방법2: yarn의 zero install을 사용하지 않을 경우
```gitignore
.pnp.*
.yarn/*
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions
```

---

## 배포
- <a href="https://vercel.com" target="_blank">Vercel</a>
- 리포지토리 등록, 배포브랜치 설정을 해주면 해당 브랜치 푸시 과정에서 CD를 지원
