一个 ts lib 的模板仓库，可以当做脚手架使用。

1. 支持单元测试与覆盖率统计
2. 使用 standard-version 或者 github action 升级版本号，产生 changelog
4. 使用 typedoc 生成文档
5. conventional commit 和相应的 hooks 的支持
6. 代码美化与语法检查的支持

## 开发之前
1. 修改`package.json`的模块信息，模块名、作者和描述。
2. 修改github workflows 里面的 package-name（改成和package.json的name一样）

### 非github项目

使用standard-version来升级版本号，然后需要手动发布。
1. 删除.github目录

### github项目
使用github action自动化发布
1. 删除npm version命令
2. 删除standard-version依赖包
3. 在github项目配置secrets：key为NPM_TOKEN，value为npm的token

## 开发与发布

### 开发

```shell
# 有变化就重新编译
npm run watch:build
# 有变化的时候使用编译过的代码进行测试
npm run watch:test
```

### 发布

github项目：
只要遵循comventional commit约定的提交，push到github之后，会自动产生merge request，合并之后就会自动发布

非github项目：
```shell
# 发布前准备，会编译、测试以及升级版本号，产生changlog
npm run prepare-release
# 推送标签和代码
git push --follow-tags origin main
# 发布到npm
npm publish
```

## 参考仓库

1. https://github.com/bitjson/typescript-starter
