<script>
  export default {
    data() {
      return {
        activeNames: ['1'],
        activeName: '1'
      };
    },
    methods: {
      handleChange(val) {
        console.log(val);
      }
    }
  }
</script>
<style>
  .demo-collapse {
    .el-collapse-item__header {
      .header-icon {
        margin-left: 5px;
      }
    }
  }
</style>

## Collapse

Use Collapse to storage content.

### Basic usage

可同时展开多个面板，面板之间不影响

:::demo
```html
<el-collapse v-model="activeNames" @change="handleChange">
  <el-collapse-item title="Consistency" name="1">
    <div>与现实生活一致：与现实生活的流程、逻辑保持一致，遵循用户习惯的语言和概念；</div>
    <div>在界面中一致：所有的元素和结构需保持一致，比如：设计样式、图标和文本、元素的位置等。</div>
  </el-collapse-item>
  <el-collapse-item title="Feedback" name="2">
    <div>控制反馈：通过界面样式和交互动效让用户可以清晰的感知自己的操作；</div>
    <div>页面反馈：操作后，通过页面元素的变化清晰地展现当前状态。</div>
  </el-collapse-item>
  <el-collapse-item title="Efficiency" name="3">
    <div>简化流程：设计简洁直观的操作流程；</div>
    <div>清晰明确：语言表达清晰且表意明确，让用户快速理解进而作出决策；</div>
    <div>帮助用户识别：界面简单直白，让用户快速识别而非回忆，减少用户记忆负担。</div>
  </el-collapse-item>
  <el-collapse-item title="Controllability" name="4">
    <div>用户决策：根据场景可给予用户操作建议或安全提示，但不能代替用户进行决策；</div>
    <div>结果可控：用户可以自由的进行操作，包括撤销、回退和终止当前操作等。</div>
  </el-collapse-item>
</el-collapse>
<script>
  export default {
    data() {
      return {
        activeNames: ['1']
      };
    }
  }
</script>
```
:::

### Accordion

At the same time only one item can be opened.

:::demo 通过 `accordion` 属性来设置是否以手风琴模式显示。
```html
<el-collapse v-model="activeName" accordion>
  <el-collapse-item title="Consistency" name="1">
    <div>与现实生活一致：与现实生活的流程、逻辑保持一致，遵循用户习惯的语言和概念；</div>
    <div>在界面中一致：所有的元素和结构需保持一致，比如：设计样式、图标和文本、元素的位置等。</div>
  </el-collapse-item>
  <el-collapse-item title="Feedback" name="2">
    <div>控制反馈：通过界面样式和交互动效让用户可以清晰的感知自己的操作；</div>
    <div>页面反馈：操作后，通过页面元素的变化清晰地展现当前状态。</div>
  </el-collapse-item>
  <el-collapse-item title="Efficiency" name="3">
    <div>简化流程：设计简洁直观的操作流程；</div>
    <div>清晰明确：语言表达清晰且表意明确，让用户快速理解进而作出决策；</div>
    <div>帮助用户识别：界面简单直白，让用户快速识别而非回忆，减少用户记忆负担。</div>
  </el-collapse-item>
  <el-collapse-item title="Controllability" name="4">
    <div>用户决策：根据场景可给予用户操作建议或安全提示，但不能代替用户进行决策；</div>
    <div>结果可控：用户可以自由的进行操作，包括撤销、回退和终止当前操作等。</div>
  </el-collapse-item>
</el-collapse>
<script>
  export default {
    data() {
      return {
        activeName: '1'
      };
    }
  }
</script>
```
:::

### Customize Title

除了可以通过 `title` 属性以外，还可以通过作用域插槽来实现自定义面板的标题内容，以实现增加图标等效果。

:::demo
```html
<el-collapse accordion>
  <el-collapse-item title="Consistency">
    <template slot="title" scope="props">
      {{props.title}}<i class="header-icon el-icon-information"></i>
    </template>
    <div>与现实生活一致：与现实生活的流程、逻辑保持一致，遵循用户习惯的语言和概念；</div>
    <div>在界面中一致：所有的元素和结构需保持一致，比如：设计样式、图标和文本、元素的位置等。</div>
  </el-collapse-item>
  <el-collapse-item title="Feedback">
    <div>控制反馈：通过界面样式和交互动效让用户可以清晰的感知自己的操作；</div>
    <div>页面反馈：操作后，通过页面元素的变化清晰地展现当前状态。</div>
  </el-collapse-item>
  <el-collapse-item title="Efficiency">
    <div>简化流程：设计简洁直观的操作流程；</div>
    <div>清晰明确：语言表达清晰且表意明确，让用户快速理解进而作出决策；</div>
    <div>帮助用户识别：界面简单直白，让用户快速识别而非回忆，减少用户记忆负担。</div>
  </el-collapse-item>
  <el-collapse-item title="Controllability">
    <div>用户决策：根据场景可给予用户操作建议或安全提示，但不能代替用户进行决策；</div>
    <div>结果可控：用户可以自由的进行操作，包括撤销、回退和终止当前操作等。</div>
  </el-collapse-item>
</el-collapse>
```
:::

### Collapse Attributes
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| accordion | whether is accordion mode | boolean | — | false |
| value | the active item's name | string/array | — | — |

### Collapse Events
| Event Name | Description | Parameters |
|---------|---------|---------|
| change | trigger when the active names change | (activeNames: array) |

### Collapse Item Attributes
| Attribute      | Description          | Type      | Accepted Values       | Default  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| name | unique identifier | string/number | — | — |
| title | title | string | — | — |