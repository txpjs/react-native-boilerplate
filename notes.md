# myapp

## 初始化 myapp

app.json 的 name、slug 字段初始化，package 的 name 字段初始化

包分析:

```js
"dependencies": {
    "@expo/vector-icons": "^13.0.0",
    "@react-navigation/bottom-tabs": "^6.0.5",
    "@react-navigation/native": "^6.0.2",
    "@react-navigation/native-stack": "^6.1.0",
    "expo": "~47.0.12",
    "expo-asset": "~8.7.0",
    "expo-constants": "~14.0.2",
    "expo-font": "~11.0.1",
    "expo-linking": "~3.3.0",
    "expo-splash-screen": "~0.17.5",
    "expo-status-bar": "~1.4.2",
    "expo-system-ui": "~2.0.1",
    "expo-web-browser": "~12.0.0",
    "react": "18.1.0",
    "react-dom": "18.1.0",
    "react-native": "0.70.5",
    "react-native-safe-area-context": "4.4.1",
    "react-native-screens": "~3.18.0",
    "react-native-web": "~0.18.9"
  },
  "devDependencies": {
    "@babel/core": "^7.12.9",
    "@types/react": "~18.0.24",
    "@types/react-native": "~0.70.6",
    "jest": "^26.6.3",
    "jest-expo": "~47.0.1",
    "react-test-renderer": "18.1.0",
    "typescript": "^4.6.3"
  },
```

## 目录修改，符合 umi 使用目录

hooks navigation constants components screens APP.tsx types.tsx 移动到 src
APP.tsx 文件内容改成引用 src 内容
screens 改成 pages
assets 改 public ，对应 app.json 的 assets 名也改成 public
space-mono 错误，搜素修改目录路径

## 增加线上打包能力

安装 eas-cli

增加命令

```js
"eas:build": "eas build -p all --profile preview",
"eas:login": "eas login",
"eas:whoami": "eas whoami",
```

app.json 增加配置

```json
"ios": {
  "bundleIdentifier": "com.txp1035.myapp"
},
"android": {
  "package": "com.txp1035.myapp"
},
```

eas 配置

```json
{
  "build": {
    "preview": {
      "android": {
        "buildType": "apk"
      },
      "ios": {
        "simulator": true
      }
    },
    "preview2": {
      "android": {
        "gradleCommand": ":app:assembleRelease"
      }
    },
    "preview3": {
      "developmentClient": true
    },
    "production": {}
  }
}
```

## ui 使用
