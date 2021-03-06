# ChangeLog

## 0.4.6 (2018-12-24)

- okam-build@0.4.6
- okam-cli@0.1.4
- okam-core@0.4.2
- okam-helper@0.4.2

### Bug Fixes

* **okam-build:** 修复 `px2rpx` 设置 `precision` 无效 ([fdbad10](https://github.com/ecomfe/okam/commit/fdbad10))
* **okam-build:** 修复构建配置对于 `entry.script` 配置的 `merge` 丢失问题 [#23](https://github.com/ecomfe/okam/issues/23) ([b2214a8](https://github.com/ecomfe/okam/commit/b2214a8))
* **okam-build:** 修复增量构建时候，重复文件输出 ([51a8bad](https://github.com/ecomfe/okam/commit/51a8bad))

### Features
* **okam-build:** 新增 `px2rpx` 插件对于 `1px` 不转换选项 ([0fb83dd](https://github.com/ecomfe/okam/commit/0fb83dd))
* **okam-build:** 新增 `Vue` 模板指令前缀支持，通过构建配置 `component.template.useVuePrefix` 启用 ([dc028b1](https://github.com/ecomfe/okam/commit/dc028b1))
* **okam-build:** 新增 `微信小程序` 和 `百度小程序`，`Vue filter` 语法支持，通过组件 `filters` 选项定义过滤器，通过构建配置 `framework` 新增 `filter` 扩展项支持 ([8bba3f1](https://github.com/ecomfe/okam/commit/8bba3f1))

### Performance Improvements

* **okam-core:** 优化数组 slice API 操作，对于 `splice(idx, 1, newValue)` 操作转成数组索引赋值操作 ([6f30d48](https://github.com/ecomfe/okam/commit/6f30d48))

### Refactor

* **okam-build:** 优化下 babel 内置 `dep` 插件的配置 ([a83a305](https://github.com/ecomfe/okam/commit/a83a305))

## okam-build@0.4.5 (2018-12-19)

### Bug Fixes

* **okam-build:** 修复 `px2rpx` 设置 `precision` 无效 ([fdbad10](https://github.com/ecomfe/okam/commit/fdbad10))
* **okam-build:** 修复模板的 `class` 绑定的对象定义换行转换失败问题 ([6c035ae](https://github.com/ecomfe/okam/commit/6c035ae))

### Features

* **okam-build:** 增加对 `百度小程序` 原生 `filter` 及 `微信小程序` `wxs` 脚本支持 ([e3a0e95](https://github.com/ecomfe/okam/commit/e3a0e95))

## okam-build@0.4.3 (2018-12-19)

### Bug Fixes

* **okam-build:** 修复入口脚本的 globalData 存在 config 导致 App 的 config 配置丢失 [#20](https://github.com/ecomfe/okam/issues/20) ([afd943e](https://github.com/ecomfe/okam/commit/afd943e))
* **okam-build:** 优化构建异步任务，对于图片处理失败依旧正常输出图片文件 [#19](https://github.com/ecomfe/okam/issues/19) ([82a01ed](https://github.com/ecomfe/okam/commit/82a01ed))

## 0.4.1 (2018-12-16)

### Bug Fixes

* **okam-build:** 修复增量构建情况下，新增组件文件输出不该输出的文件 ([c36509f](https://github.com/ecomfe/okam/commit/c36509f))
* **okam-core:** 修复自定义组件 `$emit` 的事件详情数据为空变成空对象问题，改成保留原始的事件详情数据 ([c5a55cb](https://github.com/ecomfe/okam/commit/c5a55cb))
* **okam-core:** 修复内部方法错误显示 warning 信息 ([15f32a2](https://github.com/ecomfe/okam/commit/15f32a2))
* **okam-core:** 修复 `$nextTick` 嵌套情况下，没有触发嵌套的数据修改的 `$nextTick` 回调 ([bcb2d32](https://github.com/ecomfe/okam/commit/bcb2d32))

### Features

* **okam-core:** 移除组件 `$selector` 属性，`ref` 扩展现在对于引用非自定义组件不再使用 `createSelectorQuery` 查询节点作为 fallback，即 `ref` 模板属性只能引用自定义组件，页面组件新增 `createSelectorAPI` 以对齐原生自定义组件提供的 `createSelectorQuery` API ([007410e](https://github.com/ecomfe/okam/commit/007410e))

### Refactor

* **okam-build:** 优化模板事件代理新增的模板数据属性名称长度 ([2bb0a0a](https://github.com/ecomfe/okam/commit/2bb0a0a))
* **okam-core:** 优化模板事件代理新增的模板数据属性名称长度 ([8d44206](https://github.com/ecomfe/okam/commit/8d44206))
* **okam-build:** 优化样式依赖路径的 `resolve` ([9aa7c75](https://github.com/ecomfe/okam/commit/9aa7c75))

## 0.4.0 (2018-12-06)

### Bug Fixes

* **okam-build:** 修复使用原始 `css` 样式文件，没有处理 `import css` 问题 ([6bfb038](https://github.com/ecomfe/okam/commit/6bfb038))
* **okam-build:** 修复支付宝小程序 `canvas` 组件使用 `id` 而不是微信小程序 `canvas-id` 作为组件标识符不兼容问题，统一使用 `canvas-id` ([636570b](https://github.com/ecomfe/okam/commit/636570b))
* **okam-core:** 修复微信小程序的 `canvas` 组件的事件参数对象没有 `currentTarget` 属性导致事件监听报错问题。([4e93787](https://github.com/ecomfe/okam/commit/4e93787))

### Features

* **okam-build:** 构建配置 `processors` 的处理器 `hook` 选项会重载而不是覆盖，即同一个处理器定义的多个 hook 都会被调用而不是覆盖  ([f0b318a](https://github.com/ecomfe/okam/commit/f0b318a))
* **okam-build:** 对于 `babel7` 的 `@babel/runtime` helper 代码路径进行重写：`/@babel/runtime/helpers/` 重写为 `/babel/` ([7e21c5f](https://github.com/ecomfe/okam/commit/7e21c5f))

### Refactor

* **okam-core:** 重构 `ref` 实现，原先基于 `id` 查询引用组件改成基于 `class` 避免跟开发者定义 `id` 冲突 ([86480a5](https://github.com/ecomfe/okam/commit/86480a5))
* **okam-build:** 重构 `ref` 实现，原先基于 `id` 查询引用组件改成基于 `class` 避免跟开发者定义 `id` 冲突 ([e4e95b9](https://github.com/ecomfe/okam/commit/e4e95b9))

## 0.4.0.beta-5 (2018-12-05)

### Bug Fixes

* **okam-build:** 修复头条小程序升级后模板语法报错问题，之前模板对象语法允许两个花括号，现在跟微信对齐，必须三个花括号 ([ab3d3c3](https://github.com/ecomfe/okam/commit/ab3d3c3))
* **okam-core:** 修复百度小程序从 `swan-core` `1.12` 开始会自动对自定义组件事件参数对象自动加一层包裹以对齐 `微信小程序`，即原先事件参数 `{counter: 2}` 会变成 `{type: 'counterChange', detail: {counter: 2}, counter: 2, currentTarget: {}, target: {}}`，如果碰巧你的事件参数包括 `detail` 信息，比如 `{detail: {c: 2}}` ，会导致变成 `{type: 'counterChange', detail: {detail: {c: 2}}, currentTarget: {}, target: {}}` 无法兼容原先代码。([9f82138](https://github.com/ecomfe/okam/commit/9f82138))

## 0.4.0.beta-4 (2018-12-05)

### Features

* **okam-core:** `redux` 状态管理扩展，增加 `$fireStoreChange` API 及 优化 `redux` 状态变更检查  ([0ad3bb0](https://github.com/ecomfe/okam/commit/0ad3bb0))
* **okam-core:** 增加支付宝小程序 `refs` 支持  ([c9721a4](https://github.com/ecomfe/okam/commit/c9721a4))
* **okam-build:** 增加支付宝小程序 `refs` 支持  ([44fddbe](https://github.com/ecomfe/okam/commit/44fddbe))

## 0.4.0.beta-3 (2018-12-03)

### Bug Fixes

* **okam-build:** 修复 `less` 中使用 `@import` 导致编译文件丢失问题 ([f0aca25](https://github.com/ecomfe/okam/commit/f0aca25))
* **okam-build:** 修复 `sass` `scss` 语法写法不统一导致编译出错问题 ([ee06ae6](https://github.com/ecomfe/okam/commit/ee06ae6))
* **okam-core:** 优化 `redux` 数据变更检查 [#11](https://github.com/ecomfe/okam/issues/11) ([d9d7cae](https://github.com/ecomfe/okam/commit/d9d7cae))

## 0.4.0.beta-2 (2018-12-02)

### Bug Fixes

* **okam-build:** 修复预处理语言依赖的样式文件没有编译也输出的问题 ([b1b67e4](https://github.com/ecomfe/okam/commit/b1b67e4))

## 0.4.0.beta-1 (2018-12-01)

### Bug Fixes

* **okam-build:** 修复 `win7` 下构建输出文件丢失问题 [#16](https://github.com/ecomfe/okam/issues/16) ([1fbcb40](https://github.com/ecomfe/okam/commit/1fbcb40))

## 0.4.0.beta-0 (2018-11-30)

### Features

* **okam-core:** **`break change`** 移除 App/页面/自定义组件实例上下文的 `$global` 属性([ec03a16](https://github.com/ecomfe/okam/commit/ec03a16))
* **okam-build:** **`break change`** 变更构建配置 `component.template.transformTags` 模板标签转换配置定义，新增构建 API `reverseTagMap` 进行兼容转换，具体可以查看文档
* **okam-build:** 增加特定平台相关样式定义支持: 基于媒介查询方式 ([b016e30](https://github.com/ecomfe/okam/commit/b016e30))
* **okam-build:** 增加构建配置 `script` 配置项，用于构建期间执行附加的脚本命令 ([fa7c6b4](https://github.com/ecomfe/okam/commit/fa7c6b4))
* **okam-build:** 增加构建配置 `component.global` 支持：提供全局组件自动注入能力 及 增加使用环境变量 `process.env.APP_TYPE` 定制特定平台脚本代码支持 ([ead6620](https://github.com/ecomfe/okam/commit/ead6620))
* **okam-build:** 支持特定平台配置能力支持 ([6be15a4](https://github.com/ecomfe/okam/commit/6be15a4))
* **okam-build:** 增加快应用支持、 全局 `API` 扩展支持 以及新增全局构建配置 `designWidth` 支持 ([fabbc3c](https://github.com/ecomfe/okam/commit/fabbc3c))
* **okam-build:** 增加特定平台的环境标签 Tag：`<${appType}-env>` ([c15dd06](https://github.com/ecomfe/okam/commit/c15dd06))
* **okam-build:** 增加特定平台相关样式定义支持: 基于特定平台属性前缀方式 `-${appType}-${styleProperty}: xxx` ([d028262](https://github.com/ecomfe/okam/commit/d028262))
* **okam-build:** 自动对快应用的文本内容加上 `<text></text>` 文本标签包裹 ([c860710](https://github.com/ecomfe/okam/commit/c860710))
* **okam-build:** 增加头条小程序支持 ([c516b79](https://github.com/ecomfe/okam/commit/c516b79))
* **okam-build:** 优化构建输出的资源文件：只输出依赖的资源文件，对于图片目前暂未优化，同时增加强制输出特定资源文件的能力支持 ([0097649](https://github.com/ecomfe/okam/commit/0097649))
* **okam-core:** 增加扩展平台 API 能力支持 ([548bb9c](https://github.com/ecomfe/okam/commit/548bb9c))
* **okam-core:** 增加快应用支持 ([e328420](https://github.com/ecomfe/okam/commit/e328420))
* **okam-core:** 增加 `registerApi` API for App ([1380b59](https://github.com/ecomfe/okam/commit/1380b59))
* **okam-core:** 对于 `支付宝小程序` `getSystemInfo` API 增加`SDKVersion` 属性对齐微信小程序 ([1a79383](https://github.com/ecomfe/okam/commit/1a79383))
* **okam-core:** 对于 `支付宝小程序` 增加 `setNavigationBarTitle` API 对齐微信小程序 ([dbb9b2c](https://github.com/ecomfe/okam/commit/dbb9b2c))
* **okam-core:** 增加头条小程序支持 ([20a15a2](https://github.com/ecomfe/okam/commit/20a15a2))


## okam-core@0.3.4 (2018-12-05)

### Bug Fixes

* **okam-core:** 修复百度小程序从 `swan-core` `1.12` 开始会自动对自定义组件事件参数对象自动加一层包裹以对齐 `微信小程序`，即原先事件参数 `{counter: 2}` 会变成 `{type: 'counterChange', detail: {counter: 2}, counter: 2, currentTarget: {}, target: {}}`，如果碰巧你的事件参数包括 `detail` 信息，比如 `{detail: {c: 2}}` ，会导致变成 `{type: 'counterChange', detail: {detail: {c: 2}}, currentTarget: {}, target: {}}` 无法兼容原先代码。([a47c63d](https://github.com/ecomfe/okam/commit/a47c63d))


## okam-build@0.3.3 (2018-11-30)

### Bug Fixes

* **okam-build:** 修复组件重复构建导致组件样式没有输出问题 [#13](https://github.com/ecomfe/okam/issues/13) ([96455ea](https://github.com/ecomfe/okam/commit/96455ea))

## okam-core@0.3.3 (2018-11-26)

### Bug Fixes

* **okam-core:** 修复微信小程序 computed 属性依赖的组件的 props 变化计算属性没有变化问题 [#10](https://github.com/ecomfe/okam/issues/10) ([a49f8f7](https://github.com/ecomfe/okam/commit/a49f8f7))

## 0.3.2 (2018-11-26)

### Bug Fixes

* **okam-core:** 修复 `百度小程序` 在新版 `regenerator-runtime` 下 `async await` 语法支持报错问题 ([5a621b1](https://github.com/ecomfe/okam/commit/5a621b1))

### Features

* **okam-core:** `$interceptApis` 钩子支持对返回非 Promise 的异步 API的响应数据进行改写，即支持 `done` 钩子设置 ([35b6fea](https://github.com/ecomfe/okam/commit/35b6fea))


## 0.3.1 (2018-11-15)

### Bug Fixes

* **okam-build:** 修复 `支付宝小程序` 原生事件命名风格跟其它小程序不一致问题 ([2816599](https://github.com/ecomfe/okam/commit/2816599))
* **okam-build:** 修复 `支付宝小程序` 使用原生自定义组件事件处理出错问题 [#7](https://github.com/ecomfe/okam/issues/7) ([9bc800b](https://github.com/ecomfe/okam/commit/9bc800b))
* **okam-build:** 修复 `Babel7` 处理器编译问题，API 跟 `Babel6` 不一致 ([c6a4473](https://github.com/ecomfe/okam/commit/c6a4473))
* **okam-build:** 修复 `微信小程序` 使用 `localPolyfill` 有些代码写法没有分析到情况 [#2](https://github.com/ecomfe/okam/issues/2) ([f63bbcc](https://github.com/ecomfe/okam/commit/f63bbcc))
* **okam-core:** 废弃掉 `百度小程序` 使用的 `pushData` 等内部原生 API 进行 `数组` 数据操作优化的逻辑，考虑到这些接口暂未对外开放，且还有些 Bug ([c81b323](https://github.com/ecomfe/okam/commit/c81b323))

### Features

* **okam-build:** 文件构建改成按分析依赖的顺序进行构建 ([3f44454](https://github.com/ecomfe/okam/commit/3f44454))
* **okam-cli:** 增加 CLI 工具 ([3bfc69e](https://github.com/ecomfe/okam/commit/3bfc69e))
* **okam-core:** 增加 `支付宝小程序` 原生自定义组件的 `Okam` 框架适配器 ([0efded5](https://github.com/ecomfe/okam/commit/0efded5))
* **okam-core:** 增加 `支付宝小程序` `showToast` 原生 API 的适配，保持跟微信、百度小程序的 API 的统一  ([cc8fc34](https://github.com/ecomfe/okam/commit/cc8fc34))
* **okam-core:** 增加 `支付宝小程序` 数组数据操作优化，基于 `$spliceData` API ([20be465](https://github.com/ecomfe/okam/commit/20be465))

### Performance Improvements

* **okam-core:** 优化原生 API 改写方式 ([a64f234](https://github.com/ecomfe/okam/commit/a64f234))


## 0.3.0 (2018-11-09)

### Bug Fixes

* **okam-build:** fix ant prop data observe ([a1ea9fa](https://github.com/ecomfe/okam/commit/a1ea9fa))
* **okam-core:** fix ant component prop data observe ([c061f88](https://github.com/ecomfe/okam/commit/c061f88))
* **okam-core:** fix ant custom component event emit ([fc53d2f](https://github.com/ecomfe/okam/commit/fc53d2f))
* **okam-core:** fix ant page onload data reference problem ([25b8eab](https://github.com/ecomfe/okam/commit/25b8eab))
* **okam-core:** fix mixin source plain object reference ([c8d16e6](https://github.com/ecomfe/okam/commit/c8d16e6))
* **okam-core:** fix triggerEvent none event detail case ([3581107](https://github.com/ecomfe/okam/commit/3581107))

### Features

* **okam-build:** add default babel parser options: {babelrc: false} ([7221830](https://github.com/ecomfe/okam/commit/7221830))
* **okam-build:** add native swan component event handler adapter in okam ([410dbda](https://github.com/ecomfe/okam/commit/410dbda))
* **okam-build:** disable transform click event to tap event for custom component ([60d098a](https://github.com/ecomfe/okam/commit/60d098a))
* **okam-core:** add broadcast support ([9bba7a4](https://github.com/ecomfe/okam/commit/9bba7a4))
* **okam-core:** add native swan component adapter to okam ([d1fa2ea](https://github.com/ecomfe/okam/commit/d1fa2ea))


## 0.3.0-alpha.0 (2018-11-05)

### Bug Fixes

* **okam-build:** fix ant app component page init ([0bba69c](https://github.com/ecomfe/okam/commit/0bba69c))
* **okam-build:** fix ant class template syntax ([b20abf0](https://github.com/ecomfe/okam/commit/b20abf0))
* **okam-build:** fix kebab case ref attribute value ([9302416](https://github.com/ecomfe/okam/commit/9302416))
* **okam-build:** fix not throw error when devSever not enabled in replacement processor ([c6e6176](https://github.com/ecomfe/okam/commit/c6e6176))
* **okam-build:** fix project config not exist case ([5951fe6](https://github.com/ecomfe/okam/commit/5951fe6))
* **okam-build:** fix weixin template event transformation data-* style ([824af2f](https://github.com/ecomfe/okam/commit/824af2f))
* **okam-build:** pad script file content when script exists ([85a8286](https://github.com/ecomfe/okam/commit/85a8286))
* **okam-core:** fix behavior init error in swan ([7e262b0](https://github.com/ecomfe/okam/commit/7e262b0))
* **okam-core:** fix component import path ([0433b4c](https://github.com/ecomfe/okam/commit/0433b4c))
* **okam-core:** fix extend computed prop existed in native and move extend lifecycle to methods for ant ([6e966a9](https://github.com/ecomfe/okam/commit/6e966a9))
* **okam-core:** fix native api cannot promisify ([c3247f8](https://github.com/ecomfe/okam/commit/c3247f8))
* **okam-core:** fix prop type null ([a79fa3a](https://github.com/ecomfe/okam/commit/a79fa3a))
* **okam-core:** fix ref select all not fallback node select all ([36a5d7d](https://github.com/ecomfe/okam/commit/36a5d7d))
* **okam-core:** fix request internal fetch function undefined in ant app ([2c893eb](https://github.com/ecomfe/okam/commit/2c893eb))
* **okam-core:** fix watch not work in wx custom component ([0a7cdd0](https://github.com/ecomfe/okam/commit/0a7cdd0))
* **okam-core:** remove native app component page wrap to fix ant native App/Component/Page undefined ([5dbf1f8](https://github.com/ecomfe/okam/commit/5dbf1f8))


### Features

* **okam-build:** add ant mixin support and internal mixin support ([819e3b6](https://github.com/ecomfe/okam/commit/819e3b6))
* **okam-build:** add ant template transform support ([47eb7de](https://github.com/ecomfe/okam/commit/47eb7de))
* **okam-build:** add global logger ([8a3aaa2](https://github.com/ecomfe/okam/commit/8a3aaa2))
* **okam-build:** add postcss-plugin-wx2swan ([dfd22cc](https://github.com/ecomfe/okam/commit/dfd22cc))
* **okam-build:** support ref multiple instances in template for loop ([52b14ea](https://github.com/ecomfe/okam/commit/52b14ea))
* **okam-core:** add ant mixin support ([c575126](https://github.com/ecomfe/okam/commit/c575126))
* **okam-core:** add na attribute for app/page/component ([172d58b](https://github.com/ecomfe/okam/commit/172d58b))
* **okam-core:** add wx request optimize ([d812b97](https://github.com/ecomfe/okam/commit/d812b97))
* **okam-core:** support ref multiple instances ([80fbdb2](https://github.com/ecomfe/okam/commit/80fbdb2))




