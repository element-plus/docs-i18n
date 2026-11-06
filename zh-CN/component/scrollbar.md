---
title: Scrollbar 滚动条
lang: zh-CN
---

# Scrollbar 滚动条

用于替换浏览器原生滚动条。

## 基础用法

:::demo 通过 `height` 属性设置滚动条高度，若不设置则根据父容器高度自适应。

scrollbar/basic-usage

:::

## 横向滚动

:::demo 当元素宽度大于滚动条宽度时，会显示横向滚动条。

scrollbar/horizontal-scroll

:::

## Scroll masks ^(2.14.8)

Use `mask` to indicate that more content can be scrolled to above, below, to the left, or to the right of the viewport. Masks are disabled by default.

| 值          | Behavior                                                    |
| ---------- | ----------------------------------------------------------- |
| `false`    | Disable all masks (default).                                |
| `true`     | Enable all four masks, according to the available overflow. |
| `'top'`    | Enable only the top mask.                                   |
| `'bottom'` | Enable only the bottom mask.                                |
| `'left'`   | Enable only the left mask.                                  |
| `'right'`  | Enable only the right mask.                                 |

```vue
<template>
  <el-scrollbar height="240px" mask />
  <el-scrollbar height="240px" mask="top" />
  <el-scrollbar height="240px" mask="bottom" />
  <el-scrollbar mask="left" />
  <el-scrollbar mask="right" />
</template>
```

:::demo Scroll vertically or horizontally and change the mask mode. Each enabled mask appears only while there is more content in its direction. It disappears when that edge is reached. Masks stay hidden on axes without overflow; when both axes overflow, all four masks can appear together.

scrollbar/scroll-mask

:::

Masks fade in and out over `200ms` by default, using `--el-transition-duration-fast`. The animation is disabled when the user prefers reduced motion. Masks do not block pointer events or cover scrollbar controls, and also work with `native`.

`left` and `right` refer to the physical edges of the viewport, including when the scroll container uses `direction: rtl`.

The `distance` attribute only affects the `end-reached` event; it does not change when masks appear. When using `noresize`, call `update()` after changing the content or container size to refresh the masks.

### Customize masks

Use the following CSS variables on the Scrollbar component to customize each mask:

| CSS variable                        | 说明                         | 默认值                  |
| ----------------------------------- | -------------------------- | -------------------- |
| `--el-scrollbar-top-mask-height`    | Height of the top mask.    | `40px`               |
| `--el-scrollbar-bottom-mask-height` | Height of the bottom mask. | `40px`               |
| `--el-scrollbar-left-mask-width`    | Width of the left mask.    | `40px`               |
| `--el-scrollbar-right-mask-width`   | Width of the right mask.   | `40px`               |
| `--el-scrollbar-top-mask-color`     | Color of the top mask.     | `var(--el-bg-color)` |
| `--el-scrollbar-bottom-mask-color`  | Color of the bottom mask.  | `var(--el-bg-color)` |
| `--el-scrollbar-left-mask-color`    | Color of the left mask.    | `var(--el-bg-color)` |
| `--el-scrollbar-right-mask-color`   | Color of the right mask.   | `var(--el-bg-color)` |

The default color follows the light or dark theme. Set the mask colors to match the container background when using a custom background. The example above sets the vertical mask heights and horizontal mask widths to `48px`.

## 最大高度

:::demo 当元素高度超过最大高度，才会显示滚动条。

scrollbar/max-height

:::

## 手动滚动

:::demo 通过使用 `setScrollTop` 与 `setScrollLeft` 方法，可以手动控制滚动条滚动。

scrollbar/manual-scroll

:::

## 无限滚动^(2.10.0)

:::demo `end-reached` 是在滚动条到达底部时触发的。它可以用作无限滚动。

scrollbar/infinite-scroll

:::

## API

### Attributes

| 属性名                               | 说明                                                                                     | 类型                                                                      | Default |
| --------------------------------- | -------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- | ------- |
| height                            | 滚动条高度                                                                                  | ^[string] / ^[number]                                                   | —       |
| max-height                        | 滚动条最大高度                                                                                | ^[string] / ^[number]                                                   | —       |
| native                            | 是否使用原生滚动条样式                                                                            | ^[boolean]                                                              | false   |
| wrap-style                        | 包裹容器的自定义样式                                                                             | ^[string] / ^[object]`CSSSProperties \| CSSSProperties[] \| string[]` | —       |
| wrap-class                        | 包裹容器的自定义类名                                                                             | ^[string]                                                               | —       |
| view-style                        | 视图的自定义样式                                                                               | ^[string] / ^[object]`CSSSProperties \| CSSSProperties[] \| string[]` | —       |
| view-class                        | 视图的自定义类名                                                                               | ^[string]                                                               | —       |
| noresize                          | 不响应容器尺寸变化，如果容器尺寸不会发生变化，最好设置它可以优化性能                                                     | ^[boolean]                                                              | false   |
| tag                               | 视图的元素标签                                                                                | ^[string]                                                               | div     |
| always                            | 滚动条总是显示                                                                                | ^[boolean]                                                              | 你好      |
| mask ^(2.14.8)                    | Gradient masks: `true` for all edges, a direction for one edge, and `false` to disable | ^[boolean] / ^[enum]`'top' \| 'bottom' \| 'left' \| 'right'`         | 你好      |
| min-size                          | 滚动条最小尺寸                                                                                | ^[number]                                                               | 20      |
| id ^(2.4.0)                       | 视图ID                                                                                   | ^[string]                                                               | —       |
| role ^(2.4.0) ^(a11y)             | 视图的角色                                                                                  | ^[string]                                                               | —       |
| aria-label ^(2.4.0) ^(a11y)       | 视图的 aria-label                                                                         | ^[string]                                                               | —       |
| aria-orientation ^(2.4.0) ^(a11y) | 视图的 aria-orientation                                                                   | ^[enum]`'horizontal' \| 'vertical'`                                    | —       |
| tabindex ^(2.8.3)                 | 容器的tabindex                                                                            | ^[number] / ^[string]                                                   | —       |
| distance ^(2.10.5)                | 触发到达底部事件的距离（像素）                                                                        | ^[number]                                                               | 0       |

### Events

| 事件名                   | 说明               | 类型                                                                             |
| --------------------- | ---------------- | ------------------------------------------------------------------------------ |
| scroll                | 当触发滚动事件时，返回滚动的距离 | ^[Function]`({ scrollLeft: number, scrollTop: number }) => void`            |
| end-reached ^(2.10.0) | 触发滚动结束时的触发器      | ^[Function]`(direction: 'top' \| 'bottom' \| 'left' \| 'right') => void` |

### Slots

| 插槽名     | 说明      |
| ------- | ------- |
| default | 自定义默认内容 |

### Exposes

| 名称            | Description   | 类型                                                                             |
| ------------- | ------------- | ------------------------------------------------------------------------------ |
| handleScroll  | 触发滚动事件        | ^[Function]`() => void`                                                     |
| scrollTo      | 滚动到一组特定坐标     | ^[Function]`(options: ScrollToOptions \| number, yCoord?: number) => void` |
| setScrollTop  | 设置滚动条到顶部的距离   | ^[Function]`(scrollTop: number) => void`                                    |
| setScrollLeft | 设置滚动条到左边的距离   | ^[Function]`(scrollLeft: number) => void`                                   |
| update        | 手动更新滚动条状态     | ^[Function]`() => void`                                                     |
| wrapRef       | 滚动条包裹的 ref 对象 | ^[object]`Ref<HTMLDivElement>`                                           |
