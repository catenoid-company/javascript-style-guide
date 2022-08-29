# javascript-style-guide

> eslint + prettier + airbnb style guide

### eslint
ECMAScript 코드에서 문제점을 검사하여, 코드의 가독성을 높이고 잠재적인 오류와 버그를 제거하는 것이 목적

### prettier
포매팅과 관련된 작업 수행, 좀 더 일관적인 스타일로 코드를 다듬는다.

### eslint와 prettier 통합하기
- eslint-plugin-prettier: prettier에서 인식하는 코드상의 포맷 오류를 eslint 오류로 출력
- eslint-config-prettier: prettier와 충돌하는 eslint 규칙을 끄는 역할을 한다.

### 설치
```
npm install prettier eslint-plugin-prettier eslint-config-prettier --save-dev
```

### airbnb style guide 설치
npm +5버젼을 사용중이라면 커맨드 하나로 필요 여러 라이브러리 설치
```
npx install-peerdeps --dev eslint-config-airbnb
```

커맨드 하나로 다음과 같이 라이브러리가 설치된다.
```javascript
"eslint-config-airbnb": "^19.0.4",
"eslint-plugin-import": "^2.26.0",
"eslint-plugin-jsx-a11y": "^6.6.1",
"eslint-plugin-prettier": "^4.2.1",
"eslint-plugin-react": "^7.31.0",
"eslint-plugin-react-hooks": "^4.6.0"
```

airbnb 플러그인을 적용하기 위해서는 .eslintrc.js 파일에서 extends 부분에 airbnb를 추가한다.
extends는 설치한 플러그인을 적용하기 위한 속성이다.
```javascript
module.exports = {
  env: {
    es6: true,
    node: true,
  },
  extends: ['airbnb', 'plugin:prettier/recommended'],
  rules: {},
};
```

### prettier 설정파일 예시 
```javascript
{    
    "printWidth": 80,
    "singleQuote": true,
    "semi": true,
    "tabWidth": 2,
    "trailingComma": "es5",
    "arrowParens": "always",
    "bracketSpacing": true,
    "endOfLine": "lf",
    "bracketSameLine":false
} 
```

### 자동화하는 방법
vscode에서 (ctrl or command + shift + p) default setting.json 선택
다음과 같이 추가한다. 코드 수정 후 저장할 때 마다 lint가 작동하여, 수정할 수 있는 항목에 대해서는 자동 수정한다.
```javascript
"eslint.enable": true,
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
}
```

** 관련 링크 **
- eslint: [https://eslint.org](https://eslint.org)
- prettier options: [https://prettier.io/docs/en/options.html](https://prettier.io/docs/en/options.html)
- eslint-plugin-airbnb: [https://www.npmjs.com/package/eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
- airbnb style guide: [https://github.com/airbnb/javascript](https://github.com/airbnb/javascript)
