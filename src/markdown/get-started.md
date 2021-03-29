# 开始使用

请先[安装](#/doc/install)本组件库。

然后在代码中引入组件库，例如：

```import { Button, Tab, Tabs, Switch, Dialog, Table, openDialog } from "lemon-ui"```

引入后就可以使用本组件库提供的组件了。

当然别忘记引入样式文件：

```import 'lemon-ui-1.0/dist/lib/lemon.scss'```

## 全局引入

代码示例：

```
import { createApp } from "vue";
import App from "./App.vue";
import { Button, Tab, Tabs, Switch, Dialog, Table, openDialog } from "lemon-ui"
import 'lemon-ui-1.0/dist/lib/lemon.scss';

const app = createApp(App);
app.mount("#app");
```

## 按需引入

代码示例：

```
<template>
  <div>
    <Button>按钮</Button>
  </div>
</template>
<script>
import { Button } from "lemon-ui"
import 'lemon-ui-1.0/dist/lib/lemon.scss';
export default {
  components: { Button }
}
</script>
```
