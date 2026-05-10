# UpdataSkill：OrderFollower 更新后双 Skill 同步标准操作

## 适用场景

当 `OrderFollower/SKILL.md` 发生以下任一变更时，必须执行本 SOP：
- 新增/删除/重命名阶段文件（如 `0X-xxx.md`）
- 修改阶段编号或顺序
- 修改流程图中的阶段链路
- 修改激活条件或场景确认机制
- 修改文件索引中的文件引用

---

## 阶段一：OrderFollower 自身变更

### Step 1.1 — 修改 SKILL.md 入口文件

按变更需求修改以下区域（按出现顺序）：

| # | 区域 | 检查项 |
|---|------|--------|
| 1 | `description`（YAML头） | 阶段链描述是否完整、顺序是否正确 |
| 2 | `技能定位` | 阶段链 + 核心角色描述 |
| 3 | `技能文件结构` | 文件列表是否与磁盘实际文件一一对应，编号连续 |
| 4 | `跟单全流程链路`（流程图） | 阶段顺序、分支逻辑、教练贯穿提示框 |
| 5 | `激活条件`（表格） | 每个阶段是否有对应触发词，文件引用是否正确 |
| 6 | `场景确认机制`（A~H选项） | 选项数量与阶段数量一致，描述匹配 |
| 7 | `文件索引` | 每个条目：文件引用、定位、核心方法、关键产出 |

### Step 1.2 — 创建/重命名/删除阶段文件

| 操作 | 动作 | 注意事项 |
|------|------|----------|
| 新增文件 | 创建 `0X-xxx.md` | 编号插入正确位置，后续文件无需变动 |
| 重命名 | ①写入新文件名 ②删除旧文件 | 旧文件中的**内部交叉引用**需同步更新 |
| 删除文件 | 删除文件 + 从 SKILL.md 移除引用 | 后续文件编号是否需前移 |

### Step 1.3 — 检查被重命名文件的内部交叉引用

重命名文件后，**必须**检查该文件内容中是否引用了其他已变更编号的文件。

> 示例：`05-professional-commitment.md` → `06-professional-commitment.md` 时，其内部引用了 `04-exit-decision.md`，需更新为 `05-exit-decision.md`。

**检查方法**：在被重命名的文件中搜索 `0\d-` 模式，逐一核对编号。

---

## 阶段二：OrderCoach 同步更新

### Step 2.1 — 更新 OrderCoach/SKILL.md

| # | 区域 | 检查项 |
|---|------|--------|
| 1 | `概览`段 | 阶段链描述是否与 OrderFollower 一致 |
| 2 | `方法论依赖 → 映射关系` 表格 | **逐行核对**每个训练模块引用的 OrderFollower 文件名和编号 |

**映射关系核对清单**：

```
OrderCoach 引用                       →  实际文件是否存在
01-opportunity-evaluation.md          →  OrderFollower/01-opportunity-evaluation.md
02-sales-assistant.md                 →  OrderFollower/02-sales-assistant.md
03-sales-presales-collaboration.md    →  OrderFollower/03-sales-presales-collaboration.md
04-solution-consensus.md              →  OrderFollower/04-solution-consensus.md
05-exit-decision.md                   →  OrderFollower/05-exit-decision.md
06-professional-commitment.md         →  OrderFollower/06-professional-commitment.md
07-contract-risk-control.md           →  OrderFollower/07-contract-risk-control.md
全流程 01-07                          →  与文件总数一致
```

### Step 2.2 — 更新 course-morning.md

| 检查点 | 位置 | 内容 |
|--------|------|------|
| 引用链注释 | 文件顶部 `引用链` | 引用的文件名是否正确 |
| 方法论映射表 | `OrderFollower 方法论映射` 表格 | 每个 Day 的对应文件引用 |
| 全流程范围 | 映射表 + 考核机制 | `01-0X` 范围是否覆盖全部阶段文件 |
| 考核引用 | `考核机制` 段 | 引用的具体文件名是否正确 |

### Step 2.3 — 更新 course-afternoon.md

| 检查点 | 位置 | 内容 |
|--------|------|------|
| 体系说明 | 文件顶部 `体系说明` | 引用的文件名是否正确 |
| 7天循环表 | `7天循环` 表格 | **逐行核对**每个 Day 的 `对应 OrderFollower 文件` 列 |
| 全流程范围 | Day7 行 | `01-0X` 范围是否覆盖全部阶段文件 |

### Step 2.4 — 检查 assessment-guide.md

| 检查点 | 内容 |
|--------|------|
| 框架符合度段 | 引用的具体文件名（如 `02-sales-assistant.md`）是否正确 |
| 映射表引用 | 是否正确指向 `course-morning.md` 和 `course-afternoon.md` 的映射表 |

### Step 2.5 — 检查 tracking-guide.md

该文件通常不直接引用 OrderFollower 文件，快速确认无硬编码引用即可。

---

## 阶段三：最终交叉验证

### Step 3.1 — 文件结构一致性

确认 OrderFollower 目录下的实际文件列表与 SKILL.md 中 `技能文件结构` 完全一致：

```
实际文件（按编号排序）      SKILL.md 声明
01-xxx.md                  01-xxx.md
02-xxx.md                  02-xxx.md
...                        ...
```

### Step 3.2 — 全局引用搜索

在 OrderCoach 目录下搜索所有对 OrderFollower 文件的引用：

**搜索模式**：`0\d-.*\.md`

**核对规则**：每个搜索结果中的文件名，必须在 OrderFollower 目录下实际存在。

### Step 3.3 — 全流程范围一致性

检查所有出现 `01-0X` 范围的地方，X 是否等于 OrderFollower 实际文件总数：

| 文件 | 出现位置 |
|------|----------|
| `OrderCoach/SKILL.md` | 映射表最后一行 `场景推演评估` |
| `course-morning.md` | 映射表 Day3 + 考核机制 |
| `course-afternoon.md` | 7天循环表 Day7 |

### Step 3.4 — 错误编码检查

| 错误类型 | 表现 | 检查方式 |
|----------|------|----------|
| 编号过期 | 引用了已重命名的旧编号（如 `04-exit-decision.md` 实际已是 `05`） | 逐文件搜索 `0\d-` 模式 |
| 范围过期 | `01-05` 但实际有 7 个文件 | 搜索 `01-\d` 模式 |
| 文件缺失 | SKILL.md 声明了但磁盘上不存在 | 对比文件列表 |
| 孤立文件 | 磁盘上存在但 SKILL.md 未声明 | 对比文件列表 |
| 交叉引用断裂 | 文件 A 引用了文件 B 的旧编号 | 被重命名文件中搜索 `0\d-` |

---

## 快速检查命令

在项目根目录执行以下检查：

### 1. 列出 OrderFollower 实际文件
```bash
dir /b f:\Temp\Order\OrderFollower\0*.md
```

### 2. 搜索 OrderCoach 中所有 OrderFollower 文件引用
```bash
findstr /s /r "0[1-9]-[a-z].*\.md" f:\Temp\Order\OrderCoach\*.md f:\Temp\Order\OrderCoach\references\*.md
```

### 3. 搜索所有全流程范围引用
```bash
findstr /s /r "01-0[0-9]" f:\Temp\Order\OrderCoach\*.md f:\Temp\Order\OrderCoach\references\*.md
```

---

## 变更检查清单（每次更新后逐项打勾）

### OrderFollower
- [ ] SKILL.md — description 阶段链正确
- [ ] SKILL.md — 技能定位阶段链正确
- [ ] SKILL.md — 文件结构列表与实际文件一致
- [ ] SKILL.md — 流程图阶段顺序正确
- [ ] SKILL.md — 激活条件表格文件引用正确
- [ ] SKILL.md — 场景确认选项数量匹配
- [ ] SKILL.md — 文件索引每个条目引用正确
- [ ] 新建文件已创建
- [ ] 重命名文件：新文件已写入，旧文件已删除
- [ ] 被重命名文件的内部交叉引用已更新

### OrderCoach
- [ ] SKILL.md — 概览阶段链正确
- [ ] SKILL.md — 映射表每行引用正确
- [ ] course-morning.md — 引用链注释正确
- [ ] course-morning.md — 映射表文件引用正确
- [ ] course-morning.md — 全流程范围 `01-0X` 正确
- [ ] course-afternoon.md — 体系说明引用正确
- [ ] course-afternoon.md — 7天循环表每行引用正确
- [ ] course-afternoon.md — 全流程范围 `01-0X` 正确
- [ ] assessment-guide.md — 文件引用正确
- [ ] tracking-guide.md — 无过期引用

### 交叉验证
- [ ] OrderFollower 磁盘文件 = SKILL.md 声明
- [ ] OrderCoach 所有 `0X-xxx.md` 引用在 OrderFollower 中存在
- [ ] 所有 `01-0X` 范围 = 实际文件总数
- [ ] 无孤立文件、无缺失文件、无断裂引用