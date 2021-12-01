## 在我转行前先记点东西

### 每日问题记录

```markdown

```

### React 相关

> 1.react 中图片引入的几种写法：
> 1). import testIcon from 'xxx'
> const testIcon = require('xxx')
> <img src={testIcon} alt/>
> <i style={{background: `url(${testIcon}) center/cover no-repeat`}}/>

### 数据结构和算法

```markdown

```

### JavaScript

```markdown

```

### CSS

> 1.CSS Modules
> 1).CSS Modules 结合 webpack 配置，只对 class 选择器生效，id 选择器、属性选择器并不生效；
> 2).CSS Modules 默认是启用:local 规则的，只会对:local 块的样式作规则映射，不会对:global(.className) 规则样式作处理，编译后样式原封不动；

> 2.CSS 命名技巧
> 1).BEM (B:block 对应的模块名 E:Elements 对应的节点名称 M:Modifier 表示对应的状态如 highlight hover)如 dialog_confirm-button--hightlight
> 2).CSS Modules 结合 BEM,CSS Modules 文件名对应的就是 Block,那么可以采用小驼峰的写法，表示 Element 和 Modifier,如.confirmButton--disabled
> 3).外部如何覆盖局部样式？ -》 可以在组件节点中加上属性选择器如

```markdown
<div data-role="dialog-root"></div>
[data-role="dialog-root"] {
  <!-- 因为是属性选择器所以不会被转义
  所以这里也不需要添加：global写法 -->
}
```

### Webpack

> 1.webpack 引用模块路径中包含~符号
> 原因：在引用模块字符串的最前面加上~符号，如 import '~@/style/theme';webpack 会将以~作为前缀的路径视作模块依赖去解析，这样一来别名配置就会生效，这样就不会报找不到指定目录的错误了；
> 例如：
> css module 中： @import '~@/style/theme'
> css 属性中： background: url('~@/assets/xxx.jpg')
> html 标签中： <img src="~@/assets/xxx.jpg" alt="alias">
> 参考官网解释：
> url(~module/image.png) => require('module/image.png')
> url('~module/image.png') => require('module/image.png')
> url(~aliasDirectory/image.png) => require('otherDirectory/image.png')
