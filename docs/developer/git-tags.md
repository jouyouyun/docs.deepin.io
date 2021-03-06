<!--Meta
category:系统开发
title:基于 git tag 的版本号命名规范
DO NOT Delete Meta Above -->

该文档主要介绍通过 git tag 为版本号命名的一些规范，对于 git tag 的一些
其他用法不做讨论。

# 版本号的构成

1.  版本号一般由数字 `1-9` 和 `.` 组成，不应包含多余的信息，如前端不要加字母 `v`
2.  版本号默认分为三个段位，如 `1.2.3` 。如果是 fork 的项目，版本号应在上游版本的基础上在后面增加一个子段位
3.  版本号的长度应前后保持一致，必要时做补零处理，如应使用 `1.0.0` 而不是 `1.0`
4.  如有必要，可以在版本号后面加破折号 `-` 添加更多描述信息，如 `2.3.0-loongson`

# 版本号变更规则

版本号默认分为三个段位，为方便说明，从左至右分别称之为大版本号，中版本号和小版本号，其变更规则如下：

1.  大版本号一般不做变化，除非整个项目系统架构或实现方式做重大调整
2.  中版本号的提升意味着将要发布一个新的稳定版本，此时一般会对功能接口或界面做大量调整
3.  小版本号的变更相对灵活，但在接口调整和重要 bug 修复后小版本号一定要跟进
4.  版本过渡时，若代码变更较大，一般会预先发布 `alpha` ，`beta` ，`rc`
    等测试版，此时应先在低段位添加一个大的版本号进行过渡，如 `0.2.0`
    升级至 `1.0.0` 前会先进入到 `0.90.0` ， `1.0.0` 升级至 `2.0.0` 前
    会先进入到 `1.90.0`
