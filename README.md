# JEST-TypeScript-Settings
_테스팅 도구인 jest를 사용해 typescript파일에서 작성한 코드를 테스트 해보자! <br/> 이 프로젝트는 테스팅 도구 사용을 위한 기본적인 설정을 하였습니다._

![Typescript](https://img.shields.io/badge/typescript-v4.3.4+-blue.svg)
![Yarn](https://img.shields.io/badge/yarn-brightgreen.svg)
![Jest](https://img.shields.io/badge/jest-v27.0.5+-red.svg)
<p align="center"><a href=""><img width=70% src="./asset/title.png"></a></p>

### _테스트 코드를 짜는 이유는_ <br/>
방금 구현한 기능이 잘 돌아가는지 확인하거나 <br/>
특정 기능을 변경했을 때 기존에 있던 다른 기능을 깨트리는지 확인하기 위해서입니다. <br/>

### _무엇을 어떻게 테스트 할 것인가?_ <br/>
가장 중요한 것은 무엇을 어떻게 테스트 할 것인가 인데요, <br/>
구현된 코드의 흐름이나 로직을 확인하는 것이 아니라 사용자의 관점에서 <br/> 버튼 클릭과 키 입력 등의 이벤트에 따라 UI가 올바르게 전개되는지 확인해야 합니다.

<br/>

---

## Table of Contents

- [프로젝트로 시작하기](#프로젝트로-시작하기)
  - [설치 하기](#설치-하기)
  - [테스트 하기](#테스트-하기)
- [직접 설정하기](#직접-설정하기)
  - [폴더 생성하기](#폴더-생성하기)
  - [yarn 설정 파일 생성하기](#yarn-설정-파일-생성하기)
  - [jest를 위한 라이브러리 설치하기](#jest를-위한-라이브러리-설치하기)
  - [바벨 설치하기](#바벨-설치하기)
  - [config 파일 생성하기](#config-파일-생성하기)
  - [테스트 폴더 생성하기](#테스트-폴더-생성하기)
  - [테스트 해보기](#테스트-해보기)
  - [vscode에 extension 설치하기](#vscode에-extension-설치하기)

<br/>

## 프로젝트로 시작하기

직접 라이브러리를 설정하지 않고, 프로젝트을 그대로 사용하는 방법입니다.

### 설치 하기

```
yarn install
```

### 테스트 하기

```
yarn test
```

<br/><br/>

## 직접 설정하기

직접 설정하는 경우에 아래 메뉴얼 대로 할 수 있습니다.

### 폴더 생성하기

```js
mkdir jest-test
cd jest-test
```

<br/>

### yarn 설정 파일 생성하기

- 아래 명령어를 사용하면, package.json 파일이 생성됩니다.
- 이 파일은 패키지 설정 파일이며, 라이브러리와 스크립트 정보를 정의합니다.

```js
yarn init
```

<br/>

### jest를 위한 라이브러리 설치하기

```js
yarn add -D typescript jest @types/jest ts-jest
```

<br/>

### 바벨 설치하기

- 바벨은 바벨이란 입력과 출력이 모두 자바스크립트 코드로 만들어주는 컴파일러입니다.
- 바벨을 설치하면 JSX 문법, 타입스크립트, 코드 압축, 제안 단계의 문법들을 사용할 수 있습니다.
- 타입스크립트를 사용하기 위해 바벨을 설치해주어야 합니다.

```js
yarn add --dev babel-jest @babel/core @babel/preset-env
```

<br/>

### config 파일 생성하기

- 테스트 도구인 jest에 관한 설정파일을 생성합니다. (`jest.config.js`)
- 테스트할 파일(`XXX.ts`)과 그 파일을 테스트 하는 파일(`XXX.test.ts`)은 서로 가깝게 위치해 있는 게 좋습니다.
- <a href="https://kulshekhar.github.io/ts-jest/docs/getting-started/presets/">`preset`</a>를 설정하여 jest 구성 사전 설정을 할 수 있습니다.

```js
//jest.config.js
module.exports = {
  preset: "ts-jest", //trypeScript파일은 ts-jest에서 CommonJS구문으로 변환
  testEnvironment: "node", //테스트 환경
  testMatch: ["**/*.spec.[jt]s?(x)", "**/*.test.[jt]s?(x)"], //테스트 파일 위치
};
```

<br/>

### 테스트 폴더 생성하기

- 프로젝트 루트 위치에 `__test__` 폴더를 생성합니다.

```js
mkdir __test__
```

- `__test__`에 `sample.test.ts`을 생성합니다.

```js
//__test__ / sample.test.ts
test("Dummy unit test", () => {
  const actual = 1 + 2;
  expect(actual).toBe(3);
});
```

<br/>

### 테스트 해보기

- 터미널에 아래 명령어를 입력하여 테스트가 잘 되는지 확인해보자!

```js
yarn test
```

<img src="./asset/test-example.png">

<br/>

### vscode에 extension 설치하기

- 만약 vscode를 사용하는 경우, `jest`, `jest Runner`를 설치해보세요.
- `yarn test`를 하지 않고 코드 위에 등장하는 `run` 버튼으로 바로 테스트할 수 있습니다.

```js
yarn test
```

<img src="./asset/run.png">

<br/>
<br/>
