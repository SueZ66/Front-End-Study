## Vue 2.x 功能 Tips

#### 自定义组件`v-modal`

在 2.x 中，在组件上使用 `v-model` 相当于绑定 `value` prop 并触发 `input` 事件：

```vue
<ChildComponent v-model="pageTitle" />

<!-- 是以下的简写: -->

<ChildComponent :value="pageTitle" @input="pageTitle = $event" />
```

如果想要更改 prop 或事件名称，则需要在 `ChildComponent` 组件中添加 `model` 选项：

```vue
<!-- ParentComponent.vue -->

<ChildComponent v-model="pageTitle" />
```

```vue
// ChildComponent.vue

export default {
  model: {
    prop: 'title',
    event: 'change'
  },
  props: {
    // 这将允许 `value` 属性用于其他用途
    value: String,
    // 使用 `title` 代替 `value` 作为 model 的 prop
    title: {
      type: String,
      default: 'Default title'
    }
  }
}
```

所以，在这个例子中 `v-model` 是以下的简写：

```vue
<ChildComponent :title="pageTitle" @change="pageTitle = $event" />
```



#### 使用 `v-bind.sync`

在某些情况下，我们可能需要对某一个 prop 进行“双向绑定”(除了前面用 `v-model` 绑定 prop 的情况)。为此，我们建议使用 `update:myPropName` 抛出事件。例如，对于在上一个示例中带有 `title` prop 的 `ChildComponent`，我们可以通过下面的方式将分配新 value 的意图传达给父级：

```vue
this.$emit('update:title', newValue)
```

然后父组件可以在需要时监听该事件，并更新本地的 data property。例如：

```vue
<ChildComponent :title="pageTitle" @update:title="pageTitle = $event" />
```

为了方便起见，我们可以使用 `.sync` 修饰符来缩写，如下所示：

```vue
<ChildComponent :title.sync="pageTitle" />
```

