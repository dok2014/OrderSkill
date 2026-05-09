# 晨课体系

## 体系说明

晨课是 **OrderCoach（跟单培训）** 的核心课程之一，教学内容和评估标准基于 **OrderFollower（初步跟单）** 方法论体系。

> **引用链**：OrderCoach 晨课 → OrderFollower `01-opportunity-evaluation.md`（场景判断）→ 实战训练

## 基础参数

- **推送时间**: 每日 6:00 北京时间
- **推送群**: `oc_50407ea4b5c0be2036b82af04c7c4a01`
- **循环模式**: 4天一个循环，不分工作日/节假日
- **完整迭代**: 4个循环（16天）为一个迭代周期
- **起始日**: 2026-04-24（周五）为Day1

## 4天循环

| Day | 主题 | 核心内容 |
|-----|------|----------|
| 1 | 场景判断力 | 给一个真实/模拟销售场景 → 判断客户所处阶段、核心诉求、优先级 |
| 2 | 话术演练 | 给一个具体沟通场景 → 写话术 → 优化 |
| 3 | 工作习惯复盘 | 复盘近期工作习惯 → 找改进点 → 定行动计划 |
| 4 | 销售认知升级 | 一个销售方法论/认知模型 → 拆解 → 用自己案例验证 |

## 动态天次计算

```python
import datetime

start = datetime.date(2026, 4, 24)  # Day1 (周五)
today = datetime.date.today()
delta = (today - start).days
day_in_cycle = (delta % 4) + 1
cycle_number = (delta // 4) + 1
# 标题: f"晨课第{cycle_number}轮循环的第{day_in_cycle}天：{theme}"
```

## OrderFollower 方法论映射

| Day | 主题 | 对应 OrderFollower 文件 | 评估侧重 |
|-----|------|------------------------|----------|
| 1 | 场景判断力 | `01-opportunity-evaluation.md`（BANT+MEDDIC） | 资格认证框架运用 |
| 2 | 话术演练 | `02-sales-assistant.md`（SPIN+FABE） | 沟通框架执行度 |
| 3 | 工作习惯复盘 | 全流程综合（01-05） | 执行追踪闭环 |
| 4 | 销售认知升级 | 全流程方法论提炼 | 系统思维完整性 |

## 考核机制

- **每日三问**：实战场景（今天接触了什么客户）、所用方法及效果、客户阶段判断
  - 所用方法 → 对照 OrderFollower 对应文件的标准框架评分
  - 客户阶段判断 → 对照 `01-opportunity-evaluation.md` 的决策阶段模型
- **四周考核**：完整推演考核，评估四个循环的累积效果
  - 综合参照 OrderFollower 全流程（01-05）方法论
