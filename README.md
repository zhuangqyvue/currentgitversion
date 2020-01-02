## Install

```shell
npm install currentgitversion --save-dev
```

## Quick Start
在vue-cli下build/webpack.prod.conf.js
```javascript
增加：const BuildInfo = require('currentgitversion')
在new HtmlWebpackPlugin下增加获取版本数据：
buildInfo: JSON.stringify(BuildInfo)

```

## Example
以vue-cli下build/webpack.prod.conf.js
```javascript
'use strict'
...
const BuildInfo = require('currentgitversion') //添加此处代码

const webpackConfig = merge(baseWebpackConfig, {
  ....
  plugins: [
    ...
    new HtmlWebpackPlugin({
      ....
      buildInfo: JSON.stringify(BuildInfo) //增加此处代码
    })
    ...
  ]
})
```
```javascript
然后进入index.html添加输入
<!--
 <%= htmlWebpackPlugin.options.buildInfo %>  //添加此处后npm  run build后将git信息打印上去
 -->
<!DOCTYPE html>
<html>
...
</html>
```


## update history

- 2020/01/02 1.0.0 更新 redeme 文档
