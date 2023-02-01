一个 ts lib 的模板仓库，可以当做脚手架使用。

1. 支持单元测试与覆盖率统计
2. 使用 standard-version 升级版本号，产生 changelog
3. 使用 typedoc 生成文档
4. conventional commit 和相应的 hooks 的支持
5. 代码美化与语法检查的支持

## 开发与发布

修改`package.json`的模块信息，模块名、作者和描述。

开发：

```shell
# 有变化就重新编译
npm run watch:build
# 有变化的时候使用编译过的代码进行测试
npm run watch:test
```

发布：

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
