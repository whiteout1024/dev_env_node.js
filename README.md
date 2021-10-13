# Node.js 개발환경 구축에 관한 기록

## Node.js
- Chrome에 사용되는 V8 javascript engine으로 만든 javascript runtime.
- Event 기반 non-blocking I/O model을 사용해 가볍고 효율적이라 함

## Node.js 설치
- https://nodejs.org/
LTS version을 설치하는 것이 안정성상 유리할 것으로 판단. 추천.

## Node.js package 관리
### npm
- Node.js의 기본 package 관리자
- 개발환경 구축을 위해 사용법에대한 충분한 이해 필요

1. Install/Uninstall
    1. > npm install {package name}
        1. Options 
            |     Option      |                        Description                         |
            | --------------- | ---------------------------------------------------------- |
            | -P, --save-prod | 패키지를 설치하고 프로젝트의 dependencies 목록에 추가      |
            | -D, --save-dev  | 패키지를 설치하고 프로젝트의 devDependencies 목록에 추가   |
            | -g, --global    | 패키지를 프로젝트가 아닌 시스템의 node_modules 폴더에 설치 |
            - Node.js의 workspace에는 node_modules라는 folder가 있는데, 여기에 필요한 package가 위치하고 있음
            - "npm install {package name}"의 결과는 해당 workspace의 node_modules folder에 요구한 package를 설치함
            - "npm install"의 결과는 해당 workspace의 package.json에 기록된 dependency에 따라 요구 package를 자동 설치함
1. Update
    1. > npm update
        - 현재 설치된 package에 대한 update 수행

1. Package List
    1. > npm ls
    1. > npm ls -g
    1. > npm ls -g --depth=0

1. Package Link
    1. > npm link
        - TBD.

## Typescript
- MS가 만들었으며, javascript에 data type을 추가한 super-set language.
- Compile 단계에서 명환한 type check를 통해 type이 모호한 이유에 의해 발생하는 error를 사전 검출 가능

### Node.js에서 typescript 사용
- Node.js는 기본적으로 javascirpt를 구동하기 위한 engine이므로 typescript를 직접 지원지 않음
- Typescript는 javascipt의 super-set이므로 typescript에서 javascript로 transcimpile이 가능함
- Transcomple을 통해 node.js에서 typescript를 사용할 수 있음
### 필요 package
    - typescript
    - tsc-watch
