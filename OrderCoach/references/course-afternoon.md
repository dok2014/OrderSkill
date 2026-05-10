# 午课体系 — 专业承诺技能循环

## 体系说明

午课是 **OrderCoach（跟单培训）** 的核心课程之一，教学内容围绕 **OrderFollower（初步跟单）** 中 `06-professional-commitment.md` 专业承诺方法论展开，并综合调用其他模块。

## 基础参数

- **推送时间**: 每日 12:00 北京时间
- **推送群**: `oc_50407ea4b5c0be2036b82af04c7c4a01`
- **循环模式**: 7天一个循环，不分工作日/节假日
- **起始日**: 2026-04-24（周五）为Day1

## 7天循环

| Day | 主题 | 对应 OrderFollower 文件 | 教学形式 |
|-----|------|------------------------|----------|
| 1 | 客户需求管理 | `06-professional-commitment.md`（承接情绪→量化门槛） | 场景任务 → 学员作答 → 四维度评估 |
| 2 | 沟通边界设定 | `06-professional-commitment.md`（边界设定原则） | 场景任务 → 学员作答 → 四维度评估 |
| 3 | 资源谈判技巧 | `05-exit-decision.md` + `03-sales-presales-collaboration.md` | 场景任务 → 学员作答 → 四维度评估 |
| 4 | 方案呈现优化 | `04-solution-consensus.md`（方案共识确认） | 场景任务 → 学员作答 → 四维度评估 |
| 5 | 客户期望管理 | `06-professional-commitment.md`（期望管理） | 场景任务 → 学员作答 → 四维度评估 |
| 6 | 危机处理话术 | `02-sales-assistant.md`（风险预警+沟通框架） | 场景任务 → 学员作答 → 四维度评估 |
| 7 | 综合实战演练 | 全流程（01-07）综合调用 | 总结性综合模拟测试 |

## 动态天次计算

```python
import datetime

start = datetime.date(2026, 4, 24)  # Day1 (周五)
today = datetime.date.today()
delta = (today - start).days
day_in_cycle = (delta % 7) + 1
cycle_number = (delta // 7) + 1
# 标题: f"专业承诺技能第{cycle_number}轮循环的第{day_in_cycle}天"
```

## 四维度评估反馈

学员回复后，从以下四个维度进行评估。**评估标准以 OrderFollower 对应方法论文件为基准。**

1. **框架符合度**（0-10）：参照 OrderFollower 对应文件的框架
   - 午课 → 对应 OrderFollower 文件（见本文件上方映射表）
   - 不使用框架 → 0-3｜部分使用 → 4-6｜基本遵循 → 7-8｜完整运用 → 9-10
2. **专业度评分**（0-10）：逻辑清晰度、量化程度、可行性
3. **改进建议**：具体可操作的建议，指出1-2个最关键改进点
   - 建议以 OrderFollower 方法论为改进方向
4. **参考答案**：给出一个经过优化的标准版本话术
   - 参考答案以 OrderFollower 对应方法论框架为准
