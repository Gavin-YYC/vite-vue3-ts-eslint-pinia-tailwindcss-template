# Taro Vite Vue3 TypeScript Pinia 项目模板

这是一个基于 Taro 4.x 的小程序开发模板，集成了 Vite、Vue3、TypeScript、Pinia 状态管理以及 Tailwind CSS 工具类框架，同时配置了代码规范和提交信息规范工具。

## 技术栈

- [Vite](https://vite.dev/) 4.x - 构建工具
- [Taro](https://docs.taro.zone/) 4.x - 多端统一开发解决方案
- [Vue 3](https://v3.vuejs.org/) - 渐进式 JavaScript 框架
- [TypeScript](https://www.typescriptlang.org/) - JavaScript 的超集，提供类型检查
- [Pinia](https://pinia.vuejs.org/) - Vue 状态管理库
- [Tailwind CSS](https://tailwindcss.com/) - 实用工具类优先的 CSS 框架
- [ESLint](https://eslint.org/) & [Husky](https://typicode.github.io/husky/) - 代码规范与提交规范工具

## 目录结构

```
├── config                 // 编译配置
├── dist                   // 编译后的文件
├── src                    // 源代码
│   ├── components         // 组件
│   ├── pages              // 页面
│   ├── stores             // Pinia 状态管理
│   ├── app.config.ts      // 全局配置
│   ├── app.scss           // 全局样式
│   ├── app.ts             // 入口文件
│   └── index.html         // HTML 模板
├── types                  // 类型声明
├── .eslintrc              // ESLint 配置
├── .husky                 // Git Hooks 配置
├── commitlint.config.js   // Commit 信息校验配置
├── .lintstagedrc.json     // lint-staged 配置
├── tailwind.config.js     // Tailwind CSS 配置
├── postcss.config.js      // PostCSS 配置
├── tsconfig.json          // TypeScript 配置
└── package.json           // 项目依赖
```

## 快速开始

### 环境要求

- Node.js (推荐 14.x 以上)
- 包管理工具: Yarn 或 npm

### 安装依赖

```bash
# 使用 Yarn
yarn

# 或使用 npm
npm install
```

### 运行项目

```bash
# 微信小程序
yarn dev:weapp

# H5
yarn dev:h5

# 支付宝小程序
yarn dev:alipay

# 百度小程序
yarn dev:swan

# 字节跳动小程序
yarn dev:tt

# QQ 小程序
yarn dev:qq
```

### 打包构建

```bash
# 微信小程序
yarn build:weapp

# H5
yarn build:h5

# 支付宝小程序
yarn build:alipay

# 更多平台请查看 package.json 中的 scripts
```

## Git 提交规范

项目使用 [commitlint](https://commitlint.js.org) 规范提交信息，提交格式如下:

```
<类型>: <描述>
```

支持的类型:

- `feat`: 新功能
- `fix`: 修复 bug
- `docs`: 文档修改
- `style`: 代码格式修改，不影响代码运行的变动
- `refactor`: 重构（既不是新增功能，也不是修改 bug 的代码变动）
- `perf`: 性能优化
- `test`: 添加测试
- `chore`: 构建过程或辅助工具的变动
- `revert`: 回滚到上一个版本
- `build`: 构建系统或外部依赖项的更改
- `ci`: CI 配置文件和脚本的更改

## 代码规范

项目使用 ESLint 进行代码规范检查，并通过 husky 和 lint-staged 在提交前自动检查和修复代码格式问题。

## Tailwind CSS 使用

项目集成了 Tailwind CSS，你可以在组件中直接使用 Tailwind 的工具类：

```vue
<template>
  <view class="flex items-center justify-center bg-gray-100 p-4 rounded-lg">
    <text class="text-blue-500 font-bold">Hello Tailwind!</text>
  </view>
</template>
```

## 状态管理 (Pinia)

使用 Pinia 进行状态管理，示例：

```typescript
// stores/counter.ts
import { defineStore } from 'pinia'

export const useCounterStore = defineStore('counter', {
  state: () => ({
    count: 0
  }),
  actions: {
    increment() {
      this.count++
    }
  }
})
```

```vue
// 在组件中使用
<script setup>
import { useCounterStore } from '@/stores/counter'

const counter = useCounterStore()
</script>

<template>
  <view>{{ counter.count }}</view>
  <button @click="counter.increment">+1</button>
</template>
```

## 许可证

[MIT](LICENSE)
