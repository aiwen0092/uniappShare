

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

# 安卓接受其它APP分享

组件位置：src/common/js/android/share.js

## 使用方法

* 引入

```js
import share from "../../common/js/android/share";
```

* 调用

```js
share.auth(() => {
    const ret = share.getIntent();
    if (ret?.file) {
       console.log('app-share', ret);
    }
});
```

* 返回json结构

```json
{
  "action": "android.intent.action.SEND",
  "type": "type:application/pdf",
  "uri": "content://com.android.fileexplorer.myprovider/external_files/Download/DLManager/053002400111_18540456.pdf",
  "file": "/storage/emulated/0/Download/DLManager/053002400111_18540456.pdf"
}
```

| 属性     | 名称     | 类型     | 备注        |
|--------|--------|--------|-----------|
| action | 动作     | string | 分享这里可以忽略  |
| type   | 类型     | string | 通过此属性可判别文件类型 |
| uri    | uri    | array  |           |
| file   | 本地文件路径 | array  |           |

