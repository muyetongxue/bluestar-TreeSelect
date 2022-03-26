# bluestar-TreeSelect

## 分类选择

## 引入

在script标签中引入组件

```typescript
//使用HBuilderX导入插件
import TreeSelect from "@/uni_modules/bluestar-TreeSelect/components/bluestar-TreeSelect/bluestar-TreeSelect.vue"

//使用npm install
import TreeSelect from "bluestar-treeselect/components/bluestar-TreeSelect/bluestar-TreeSelect.vue"
```

## 代码演示

```vue

<template>
	<view class="test">
		<TreeSelect color="#36D6B6" :left-items="leftItems" :right-items="rightItems" @click-nav="clickNav">
			<!--自定义左侧显示字段名-->
			<template v-slot:left-text="slotProps">
				{{ slotProps.value.text }}
			</template>
			<!--自定义右侧模板-->
			<template v-slot:right="slotProps">
				<view class="card">{{ slotProps.value.text }}</view>
			</template>
		</TreeSelect>
	</view>
</template>

<script setup lang="ts">
import {reactive} from "vue"

const leftItems = reactive([
	{
		text : '左侧选项一',
	},
	{
		text : '左侧选项二',
	},
	{
		text : '左侧选项三',
		disabled : true
	},
])
const rightItems = reactive([
	{
		text : '右侧选项一',
	},
	{
		text : '右侧选项二',
	},
	{
		text : '右侧选项三',
	},
	{
		text : '右侧选项四',
	},
	{
		text : '右侧选项五',
	},
	{
		text : '右侧选项六',
	},
])

const clickNav = (value : any, index : number) => {
	console.log(value)
	console.log(index)
}
</script>

<style lang="scss" scoped>
.card {
	width: 100%;
	height: vw(100);
	border: vw(2) solid #e1e1e1;
	border-radius: vw(10);
	margin: 0 0 vw(20) 0;
}
</style>
```

## API

#### Props

| 参数        | 说明       | 类型        | 默认值     |
|-----------|:---------|:----------|:--------|
| left-items | 左侧导航所需数据 | `Array`   | []      |
| right-items   | 右侧内容所需数据 | `Array`  | []      |
| color     | 主题色      | `string`  | #0E75FC |

#### Events

| 事件名称 | 说明      | 回调参数     |
| :----- |:--------|----------|
| bing:click-nav | 左侧导航点击时，触发的事件 | 选中值,选中索引 |

#### Slots

| 事件名称 | 说明                     |
| :----- |:-------------------------|
| left-text | 自定义左侧显示字段名  |
| right | 自定义右侧模板  |

#### left-items数据结构

考虑到现有业务范围和接口返回模型，暂未提供子选项children渲染右侧数组。

```json
[
  {
    // 禁用选项
    "disabled": false
  }
]
```

## 作者

![](https://img.shields.io/static/v1?label=蓝星软件&message=@caisheng&labelColor=0E75FC)
