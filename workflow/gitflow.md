# Git Flow

## 两个长期分支

1. master：主分支，即线上分支，存放对外发布的版本
2. development：开发分支，用于日常开发，存放最新的开发版

## 三个短期分支

**feature**

功能分支，从 development 分支分出，开发完再合并到 development 分支。

```
git checkout -b feature-xxx development

开发中...

git checkout development

git merge --no-ff feature-xxx

git branch -d feature-xxx
```

**release**

预发布分支（测试），从 development 分支创建，测试成功后合并到 master 分支，并打个标签，然后再合并到 development 分支，最后删除预发布分支。

```
git checkout -b release-0.1.0 development

测试中...

git checkout master

git merge --no-ff release-0.1.0

git tag -a v0.1.0 -m 'xxx'

git checkout development

git merge --no-ff release-0.1.0

git branch -d release-0.1.0
```

**hotfix**

修复线上BUG，首先从 master 分支上创建 hotfix 分支，修改BUG，改完后合并到 master 分支并打标签，然后再合并到 development 分支，最后删除 hotfix 分支。

```
git checkout -b hotfix-xxx master

修复 BUG 中...

git checkout master

git merge --no-ff hotfix-xxx

git tag -a v0.1.1 -m 'xxx'

git checkout development

git merge --no-ff hotfix-xxx

git branch -d hotfix-xxx
```
