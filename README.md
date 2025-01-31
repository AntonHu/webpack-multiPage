# 从零配置的webpack多页面应用

## 配置目录
```
.
├── config ------------------- webpack构建配置目录
    ├── config.utils.js -------- 抽离辅助构建的一些工具方法
    ├── webpack.base.js ------- 常规的基础配置
    ├── webpack.dev.js ------------ 开发环境配置
    ├── webpack.prod.js ----- 生成环境配置
```

## 新增页面

1. 在 **pages** 目录下新建页面文件夹
2. 在文件夹下创建jsx，tsx，js，ts文件皆可作为本页面打包的入口文件
3. 可在上述文件夹内创建同名html文件，可作为模板打包最终的html，不添加则使用 **src/index.html** 作为默认模板

## 项目构建
项目构建支持指定page参数，只构建一个页面，不指定则同时构建所有页面：
```bash
yarn start page=yourPageName // 项目启动，page参数可选
```
```bash
yarn dev page=yourPageName // 项目测试环境打包，page参数可选，生成环境yarn prod
```
打包生产建议全量打包，这样可以使用模块拆分等打包优化的能力

## 工程化配置
本项目还集成了

| 工具        | 介绍                         | 配置                    |
| ----------- | ---------------------------- | ----------------------- |
| Eslint      | es风格检查工具               | .eslintrc.js            |
| Prettier    | 代码格式化工具               | .prettierrc.js          |
| Lint-staged | 对暂存区内容进行指定脚本处理 | packagejson/lint-staged |
| Husky       | 提供git相关钩子              | package.json/husky      |
| PostCSS     | 简化css的预处理              | postcss.config.js       |
| Babel       | 转译非js代码                 | .babelrc.js             |
| Typescript  | ts配置                       | .tsconfig.json          |
