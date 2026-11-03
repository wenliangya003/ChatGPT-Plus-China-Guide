# Codex 日常使用指南

更新于：2026-11-03

用 Codex 阅读项目、修复问题、补充测试或整理文档，可以从下面这套流程开始。

## 1. 打开项目

在桌面客户端打开项目文件夹，或在已有项目中使用 Codex CLI、IDE 扩展。安装和入口说明见 [OpenAI 官方快速开始](https://learn.chatgpt.com/docs/quickstart)。

使用 ChatGPT 登录可使用套餐内的 Codex 权益；Plus 已包含 Codex。套餐与额度见 [OpenAI 官方价格说明](https://learn.chatgpt.com/docs/pricing)，登录方式见 [官方登录说明](https://learn.chatgpt.com/docs/auth)。

先确认登录的是持有订阅的 ChatGPT 账号。API Key 登录按 API 价格单独计费，不会自动使用 Plus 额度。

## 2. 先理解项目

第一次接触项目时，可以发送：

```text
先阅读 README、项目说明和与任务相关的代码，暂不修改文件。

请说明：
1. 项目如何启动；
2. 主要目录和核心模块各负责什么；
3. 已有测试如何运行；
4. 如果要修改登录页面，应从哪些文件入手。

每项给出对应的文件路径。
```

把“登录页面”换成你准备处理的具体功能，就能将阅读范围集中到当前任务。

## 3. 一次完成一个具体修改

描述问题时，给出复现步骤、当前结果和预期结果。例如：

```text
请修复登录表单的问题：
- 复现步骤：邮箱留空，填写密码，点击登录；
- 当前结果：页面没有反馈；
- 预期结果：显示“请输入邮箱”。

沿用项目现有的表单和提示样式，并补充覆盖此问题的测试。
完成后说明修改的文件、实现方式和测试结果。
```

日常任务也可以这样描述：

| 任务 | 可以提供的信息 |
| --- | --- |
| 排查报错 | 完整报错、触发步骤、相关文件 |
| 调整页面 | 页面位置、目标效果、现有设计参考 |
| 重构模块 | 目标模块、要改善的问题、应保持的行为 |
| 维护文档 | 目标文件、需要更新的事实、可核对的来源 |

## 4. 检查结果

修改完成后，可以继续发送：

```text
请检查本次修改的 diff，并运行与修改相关的现有检查或测试。

请返回：
1. 修改摘要和文件列表；
2. 实际运行的命令及结果；
3. 尚未完成的检查和具体原因。

如果涉及页面交互，请给出可手动复现的验证步骤。
```

阅读实际 diff，结合测试输出或页面操作结果判断修改是否符合预期。对于没有测试的文档项目，可以先检查链接、文件路径和 Markdown 渲染结果。

## 5. 额度与后续任务

Codex 的用量会受到模型、任务复杂度和上下文大小影响。当前额度与重置时间以账号的用量页面为准，见 [官方额度说明](https://learn.chatgpt.com/docs/pricing)。

ChatGPT Work 与 Codex 共用用量。达到限额时，先查看用量与重置时间，再决定是否等待或购买额外额度。

继续下一项任务时，说明新的目标、相关文件和验收条件。需要重复处理的项目约定，可以整理进项目的 `AGENTS.md`；具体用法见 [OpenAI 官方项目指令说明](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

## 6. 登录与额度问题速查

| 遇到的问题 | 先核对什么 |
| --- | --- |
| 买了 Plus，但 Codex 未显示对应权益 | 查看当前账号和登录方式，确认与购买订阅的 ChatGPT 账号一致；再核对[订阅归属](https://help.openai.com/en/articles/20001056-troubleshooting-chatgpt-subscription-access-and-account-changes) |
| 被要求输入 API Key | 想使用套餐额度时，选择 Sign in with ChatGPT；API Key 是另一种计费方式，见[官方登录说明](https://learn.chatgpt.com/docs/auth) |
| 提示达到用量上限 | 查看账号用量与重置时间；Codex CLI 会话可用 `/status` 查看当前状态，见[官方额度说明](https://learn.chatgpt.com/docs/pricing) |

[开通方式与付款问题排查](plus-subscription-guide.md) · [返回 ChatGPT Plus 开通指南](../README.md)
