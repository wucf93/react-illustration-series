# 图解 React 原理系列

> `react`原理, 基于[`react@17.0.1`](https://github.com/facebook/react/tree/v17.0.1)(尽可能跟随 react 版本的升级, 持续更新). 用大量配图的方式, 致力于将`react`原理表述清楚.

## 使用指南

1. 本系列以 react 核心包结构和运行机制为主线索进行展开. 包括`react 宏观结构`, `react 工作循环`, `react 启动模式`, `react fiber原理`, `react hook原理`, `react 合成事件`等核心内容.
2. 开源作品需要社区的净化和参与, 如有表述不清晰或表述错误, 欢迎[issue 勘误](https://github.com/7kms/react-illustration-series/issues). 如果对你有帮助, 请不吝 star.
3. 本系列最初写作于 2020 年 6 月(当时稳定版本是 v16.13.1), 随着 react 官方的升级, 本 repo 会将主要版本的文章保存在以版本号命名的分支中, 可以切换分支进行阅读(最新分支为 17.0.1, 由于工作原因, 更新进度受到影响, 正在尽力写作中).
4. 当下前端技术圈总体比较浮躁, 各技术平台充斥着不少"标题党". 真正对于技术本身, 不能急于求成, 需要静下心来修炼.
5. 本系列不是面经, 但会列举一些面试题来加深对 react 理解.
6. 本系列所有内容皆为原创, 如需转载, 请注明出处.

## 适用读者

1. 对`react`,`react-dom`开发 web 应用有实践经验.
2. 期望深入理解`react`内在作用原理.

---

## 重要更新

react@17 到目前(2020 年 11 月 30 日)共有 2 个版本的发布([`react@17.0.0`](https://github.com/facebook/react/tree/v17.0.0), [`react@17.0.1`](https://github.com/facebook/react/tree/v17.0.1)), 其中`v17.0.0`作为主版本升级(具体变动详见官方[更新日志](https://github.com/facebook/react/blob/master/CHANGELOG.md#1700-october-20-2020))相较于 16.x 版本, 在使用层面基本维持不变, 在源码层面需要关注的重大的变动如下

| 重大变动                                                      | 所属板块                                    | 官方解释                                                                                                      |
| ------------------------------------------------------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| 重构`Fiber.expirationTime`并引入`Fiber.lanes`                 | `react-reconciler`                          | [Initial Lanes implementation #18796](https://github.com/facebook/react/pull/18796)                           |
| 事件代理节点从 document 变成 rootNode, 取消合成事件的缓存池等 | `legacy-events(被移除)`, `react-dom/events` | [changes-to-event-delegation](https://reactjs.org/blog/2020/10/20/react-v17.html#changes-to-event-delegation) |

## 主要类容

### 基本概念

- [宏观包结构](./docs/main/macro-structure.md)
- [两大工作循环](./docs/main/workloop.md)
- [高频对象](./docs/main/object-structure.md)

### 运行核心

- [reconciler 运作流程](./docs/main/reconciler-workflow.md)
- [启动过程](./docs/main/bootstrap.md)
- [优先级管理](./docs/main/priority.md)
- [scheduler 调度原理](./docs/main/scheduler.md)
- [fiber 树构造(基础准备)](./docs/main/fibertree-prepare.md)
- [fiber 树构造(初次创建)](./docs/main/fibertree-create.md)
- fiber 树构造(对比更新)
- fiber 树渲染
- 异常处理

### 数据管理

- 状态组件(`class`)
- 状态组件(`function`)
- hook 原理(`useState`)
- hook 原理(`useEffect`)
- context 原理

### 交互

- 合成事件原理

### 高频算法

- [位运算](./docs/algorithm/bitfiled.md)
- [堆排序](./docs/algorithm/heapsort.md)
- [深度优先遍历](./docs/algorithm/dfs.md)
- [链表操作](./docs/algorithm/linkedlist.md)
- [栈操作](./docs/algorithm/stack.md)
- [diff 算法](./docs/algorithm/diff.md)

## 历史版本

- [基于 v16.13.1 版本的分析](https://github.com/7kms/react-illustration-series/tree/v16.13.1)
- [基于 v17.0.1 版本的分析](https://github.com/7kms/react-illustration-series/tree/v17.0.1)
