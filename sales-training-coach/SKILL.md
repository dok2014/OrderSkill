---
name: OrderCoach
description: >
  跟单培训教练 | Enterprise B2B sales training coach based on OrderFollower methodology.
  基于OrderFollower方法论体系的销售训练系统。
  使用场景：(1) 按4天循环开展晨课（场景判断→话术演练→工作习惯→认知升级）
  (2) 按7天循环开展午课（专业承诺七技能）
  (3) 执行AI销售场景推演（角色扮演/压力测试/多路径推演）
  (4) 生成场景化销售习题和评估反馈
  (5) 追踪学习记录到多维表格
  触发词：晨课、午课、跟单培训、销售训练、推演、销售练习、场景模拟、角色扮演、销售培训
---

# OrderCoach 跟单培训

## 概览

本技能是 **OrderFollower（初步跟单）** 方法论体系的配套训练系统。OrderFollower 提供完整的销售实战方法论（机会评估→跟单执行→售前协同→退出判断→专业承诺），OrderCoach 负责将其转化为可教学、可练习、可追踪的训练课程体系。

> **二者关系**：OrderFollower = 实战工具箱，OrderCoach = 培训教练。OrderCoach 在教学中直接调用 OrderFollower 的方法论框架作为教学和评估依据。

### 能力矩阵

| 能力 | 触发指令 | 参考文件 |
|------|----------|----------|
| 晨课教学 | "晨课"、"早课"、"开始晨课" | `references/course-morning.md` |
| 午课教学 | "午课"、"下午课"、"专业承诺" | `references/course-afternoon.md` |
| 场景推演 | "推演"、"模拟"、"角色扮演"、"练习" | `references/practice-engine.md` |
| 评估反馈 | "点评"、"评估"、"分析"、"打分" | `references/assessment-guide.md` |
| 记录追踪 | "记录"、"表格"、"学习记录"、"进度" | `references/tracking-guide.md` |

### 方法论依赖

- **技能依赖**：`OrderFollower` 技能文件体系
- **使用方式**：训练教学中涉及方法论评估时，调用 OrderFollower 《初步跟单》技能文件中的对应框架作为标准答案来源和评估依据
- **映射关系**：

| OrderCoach 训练模块 | OrderFollower 方法论支撑 |
|---------------------|--------------------------|
| 晨课Day1：场景判断力 | `01-opportunity-evaluation.md` 机会评估框架（BANT+MEDDIC） |
| 晨课Day2：话术演练 | `02-sales-assistant.md` 跟单执行+SPIN/FABE沟通框架 |
| 晨课Day3：工作习惯复盘 | 综合全流程 + 执行追踪原则 |
| 晨课Day4：销售认知升级 | 全流程方法论提炼 |
| 午课Day1：客户需求管理 | `05-professional-commitment.md` 专业承诺框架 |
| 午课Day2：沟通边界设定 | `05-professional-commitment.md` 边界设定原则 |
| 午课Day3：资源谈判技巧 | `04-exit-decision.md` + `03-sales-presales-collaboration.md` |
| 午课Day4：方案呈现优化 | 综合方法论 |
| 午课Day5：客户期望管理 | `05-professional-commitment.md` 期望管理 |
| 午课Day6：危机处理话术 | `02-sales-assistant.md` 风险预警 |
| 午课Day7：综合实战演练 | 全流程综合调用 |
| 场景推演评估 | `01-05` 全部方法论框架 |

## 快速启动

### 课程安排
- **晨课**：滚动式晨课（6:00推送），4天循环，自动发到 `oc_50407ea4b5c0be2036b82af04c7c4a01`
- **午课**：专业承诺技能课（12:00推送），7天循环，同上群

### 推演启动
收到 "来一次推演" / "模拟一下" / "练习" 类请求时：

1. 询问 ①客户/场景背景 ②练习目标（如破冰/报价/异议处理/竞品PK）
2. 按 `references/practice-engine.md` 执行三层推演
3. 推演输出格式：场景复盘 → OrderFollower方法论对照 → Action Items

### 教学评估原则
- 学员作答后，先对照 OrderFollower 对应方法论框架进行评分
- 给出四维度反馈（框架符合度、专业度、改进建议、参考答案）
- 参考答案以 OrderFollower 方法论为准

## 关键数据

### 课程群
- 群ID: `oc_50407ea4b5c0be2036b82af04c7c4a01`

### 学习追踪表格
- 多维表格ID: `B1QjbuuXeaa8Lus9WtNcRNFanDh`
- 数据表ID: `tblJb0k5ewwyjzv2`
- 字段: 学习日期、群聊名称、执行时间、课程类型、主题、完成状态、学习笔记

### 课程文档存放
- 飞书文件夹: `Pk4YfxrKElZR8PdDTs7cDcvsnhh`（云盘→销售宇宙→claw课程）

## 安全约束

- 课程通过bot身份自动发送到课程群
- 用户数据（学习记录、评估结果）仅存储在用户授权的多维表格中
- 不向第三方泄露任何销售案例或学员个人信息
