# 开始使用

请先[安装](#/doc/install)本组件库。

然后在代码中引入组件库，例如：

```import {Button, Tabs, Switch, Dialog} from "lemon-ui"```

引入后就可以使用本组件库提供的组件了。

## Vue 单文件组件

代码示例：

```
<template>
  <div>
    <Button>按钮</Button>
  </div>
</template>
<script>
import {Button, Tabs, Switch, Dialog} from "lemon-ui"
export default {
  components: {Button}
}
</script>
```
