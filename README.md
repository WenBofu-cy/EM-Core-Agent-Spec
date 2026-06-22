# EM-Core Agent V1.1

**端侧原生三层解耦认知-记忆-执行通用 AI Agent 架构**

> 版本：V1.1 ｜ 日期：2026-06-22
> 原创提出者：文波福
> 开源协议：CC BY 4.0（署名 4.0 国际许可证）
> 架构同源：EM-Core HR人形机器人 / EM-Core AD自动驾驶


## 项目简介

EM-Core Agent 是一套完全端侧原生、认知-记忆-执行彻底解耦、全链路时序闭环、可终身自成长、可跨设备迁移、可工程标准化量产的新一代通用 AI Agent 基础架构。

区别于行业主流“Prompt 串联 + 向量检索”的轻量化拼凑式 Agent，EM-Core 采用类人仿生三层中枢架构，完整继承 EM-Core 人形机器人原生智能内核，仅轻量化复用自动驾驶体系的「双漏斗隔离机制」，专为纯数字智能体重构出一套轻量、干净、可收敛、可长期迭代不崩坏的端侧智能底座。


## 三中枢架构

```
ECC 认知大脑（12模块）→ MLNF 记忆中枢（60模块）→ MCC 执行小脑（40模块）
       决策层                  经验层                  执行层
```

| 仓库 | 模块数 | 定位 | 核心职责 |
|------|:---:|------|----------|
| [agent-ecc-brain](https://gitee.com/expanding-research/agent-ecc-brain) | 12 | 认知大脑 | 唯一意图理解、唯一安全仲裁、唯一全局调度 |
| [agent-mlnf-mem](https://gitee.com/expanding-research/agent-mlnf-mem) | 60 | 双漏斗记忆中枢 | 用户画像沉淀、任务经验进化、宏观自收敛 |
| [agent-mcc-exec](https://gitee.com/expanding-research/agent-mcc-exec) | 40 | 工具执行中枢 | 跨平台原子操作、全链路并发调度、故障自愈 |


## 核心特性

| 特性 | 说明 |
|------|------|
| 认知-记忆-执行彻底解耦 | ECC 只决策不执行，MCC 只执行不思考，MLNF 只沉淀不推理 |
| 双漏斗终身记忆 | 漏斗一用户画像，漏斗二 Agent 自成长经验，五层单向晋升 |
| 宏观自收敛 | 子漏斗达上限后自动归并，行为风格长期稳定不漂移 |
| 三层安全拦截 | 网关分片预检 + ECC语义签名 + MCC底层资源锁兜底 |
| 双签名强制准入 | 所有执行报文必须携带 sign_ecc05 + sign_mcc02 |
| 多会话并发调度 | 跨 session 隔离并行 + 同 session DAG 智能并行 |
| 会话只读锁 | LLM调用即下发锁，全会话任务成功方可解锁记忆写入 |
| 七类故障分级处理 | F/A/N/C/B/R/H 故障自动分类，可重试自动退避 |
| 操作撤销与崩溃恢复 | 分支独立快照栈 + WAL预写日志 + 断点续传 |
| 端侧离线运行 | 本地推理引擎兜底，日常任务完全离线，零云端依赖 |
| 记忆一键迁移 | L4/L5 加密导出/导入，一台Agent学会一键复制到另一台 |
| 跨设备会话同步 | 局域网加密直连，手机电脑无缝切换继续对话 |


## 双总线通信体系

| 总线 | 连接中枢 | 传输内容 |
|------|----------|----------|
| MemoryBus | ECC ↔ MLNF-Mem | 记忆检索、经验写入、I值同步、会话锁指令 |
| CerebellumBus | ECC ↔ MCC | 任务下发、DAG调度、执行回执、故障上报、熔断信号 |


## 子仓库

| 仓库 | 模块数 | 说明 |
|------|:---:|------|
| [agent-ecc-brain](https://gitee.com/expanding-research/agent-ecc-brain) | 12 | 认知大脑 |
| [agent-mlnf-mem](https://gitee.com/expanding-research/agent-mlnf-mem) | 60 | 双漏斗记忆中枢 |
| [agent-mcc-exec](https://gitee.com/expanding-research/agent-mcc-exec) | 40 | 工具执行中枢 |


## 文档

| 文档 | 说明 |
|------|------|
| [技术白皮书 V1.1](WHITEPAPER.md) | 完整架构理论与设计思想 |
| [商业使用许可](LICENSE-COMMERCIAL.md) | 商业合作与授权说明 |
| MemoryBus 总线规范 | 各子仓库 `spec/bus_memory.md` |
| CerebellumBus 总线规范 | 各子仓库 `spec/bus_cerebellum.md` |


## 开源协议

本项目采用 **CC BY 4.0（署名 4.0 国际许可证）** 全球开源授权。

- 个人、团队、企业可免费使用、修改、二次开发、商用产品落地
- 必须显著保留原作者署名：**文波福**
- 架构首创权永久归属原作者，不可剥夺、不可转移

商业合作请联系：710705008@qq.com