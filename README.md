# React TS LoginTest Frontend
이 프로젝트는 [Create React App](https://github.com/facebook/create-react-app)로 생성되었습니다.
react, typescript, react-redux- react-router, typesafe-actions를 사용하여 구현하였습니다.

## File Structure
```
React-Ts-LoginTest-Frontend
│
├── public
├── src
│   ├── api
│   │   └── reqres.ts
│   ├── assets
│   │   ├── css
│   │   │   ├── App.css
│   │   │   └── index.css
│   │   └── img
│   │       └── logo.svg
│   ├── components
│   │   └── PrivateRoute.tsx
│   ├── hooks
│   │   ├── useAuthentication.tsx
│   │   └── useLogin.tsx
│   ├── modules
│   │   ├── login
│   │   │   ├── actions.ts
│   │   │   ├── index.ts
│   │   │   ├── reducer.ts
│   │   │   └── types.ts
│   │   └── index.ts
│   ├── views
│   │   ├── App.test.tsx
│   │   ├── App.tsx
│   │   ├── Dashboard.tsx
│   │   ├── Login.tsx
│   │   └── Mypage.tsx
│   ├── index.tsx
│   ├── react-app-env.d.ts
│   ├── routes.tsx
│   ├── serviceWorker.ts
│   └── setupTests.ts
├── data.json
├── pakage.json
├── README.md
├── tsconfig.json
└── yarn.lock    
```

## GetStart

### Create Project & Update
CRA를 사용하여 react-ts-logintest-frontend를 생성합니다.
```
$ npx create-react-app react-ts-logintest-frontend --typescript
```
typescript 3.7 버전과  eslint 2.24 버전과의 호환 문제가 있어 typescript 3.8.3로 업그레이드가 필요합니다.
추후 CRA에서 typescript 3.8이상을 자동 생성하게 되면 업데이트 할 필요 없습니다.
```
$ yarn upgrade typescript@^3.8.3
```

### Add Library
필요한 라이브러리인 react-router, redux, axios, typesafe-actions를 추가합니다.
``` 
$ yarn add react-router-dom @types/react-router-dom react-redux @types/react-redux axios @types/axios typesafe-actions 
```

### IE 11 설정
```
$ yarn add react-app-polyfill
```
package.json에서 ie 11를 추가합니다.
```
"browserslist": {
  "production": [
    ">0.2%",
    "not dead",
    "not op_mini all",
    "ie 11"
  ],
  "development": [
    "last 1 chrome version",
    "last 1 firefox version",
    "last 1 safari version",
    "ie 11"
  ]
}
```
index.tsx 맨 위에 import 2개를 추가합니다.
```
import 'react-app-polyfill/ie11';
import 'react-app-polyfill/stable';
```
IE 11 세팅이 완료되었습니다.   
위 설정 후에도 IE에서 실행이 되지 않으면 node_modules/.cache를 삭제 후 다시 yarn start 하면 됩니다.

### JSON-SERVER
axios 연동을 위한 json-server를 생성 및 실행합니다.   
최상위 폴더에 data.json를 생성 후 아래 내용을 입력합니다.
```
{
  "auth": {
    "authentication": "jwt-tokken"
  }
}
```
아래 명령어를 이용하여 json-server를 실행할 수 있습니다.
```
$ npx json-server ./data.json --port 4000

localhost가 아닌 다른 호스트를 지정하기 위해선 --host 옵션을 추가하면 됩니다.
$ npx json-server ./data.json --host 10.10.1.10 --port 4000
```
[http://localhost:4000/auth](http://localhost:4000/auth)를 접속하여 확인 할 수 있습니다.


## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).
