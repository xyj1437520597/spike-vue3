# Spike-vue3

![](https://img.shields.io/badge/license-MIT-000000.svg)

> 本组件库仅供学习交流，请勿在生产环境中使用

<!-- [官方文档](https://xue-ui.com.cn)   
[React 实现](https://github.com/BlameDeng/xue-react) -->

## 安装

克隆官方仓库或者使用 npm / yarn 安装

```

$ npm install spike-vue3
$ yarn add spike-vue3
```

## 使用

如果使用了 npm / yarn 安装，一般在 main.js 中如下配置：

```javascript
import { sButton } from "spike-vue3"
import 'spike-vue3/package/lib/spike-vue3.css'
export default {
  components: {
    sButton,
  }
}
```

以上代码便完成了 spike-vue3 的引入。需要注意的是，样式文件需要单独引入。

## 特别提醒

使用 spike-vue3 时，您需要使用 border-box 盒模型，否则会影响样式。代码示例：

```css
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

如果您觉得还不错，请 star