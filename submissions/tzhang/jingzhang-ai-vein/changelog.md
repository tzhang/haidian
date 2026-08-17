# 方案迭代记录 · 京张智脉 JingZhang AI Vein

## v0.1 - 2026-08-08

### 改动摘要

- 建立"京张智脉"总体概念：一带(智脉绿脊)三核(众智园·智创源/原点社区·智汇谷/大钟寺·智享城)两翼(中关村科技服务翼/小月河场景赋能翼)五园(北航/北邮/北交/北理工/北科高校协同带)。
- 生成完整 formal 提交包：16地块用地全覆盖零重叠、蓝绿34.2%、科研35.8%；12张AI场景卡+3个测试验证场景+5类用户画像+3个AI朝圣地标+年度活动体系。
- 5张演示级图件、5页A3文册、2页A0展板、离线visual/index.html全部生成。
- 自检结果：PASS（formal-review-ready）；空间审查、视觉包装、专业证据审查全部通过。

### 采纳反馈

- 暂无，首版提交。已按规则读取 design_brief / agent_taskbook / source_registry / planning_limits。

### 暂未采纳或待复核事项

- 官方 SITE_BOUNDARY / KEY_AREA polygon 缺失，采用 provisional 粗略边界（与官方面积吻合），正式数据发布后需全部复算。
- 容积率、建筑高度、建筑密度、道路红线、绿地率红线等控规条件缺失，metrics.json 全部标 unknown，正文标注"待确认"，不编造精确值。
- 具体地块拆改留、轨道站点工程、市政管线方案均待正式控规/权属/工程条件确认。

### 公开资料与合规说明

- 本版本仅使用组织方清权公开资料（source_registry 登记），未使用非公开规划图件、非公开空间数据、个人隐私数据；未伪造官方背书或规划结论。
- 全部空间判断为开放共创概念建议，不替代正式规划，不构成政府审定结论。

## v1.1 - 2026-08-09

### 改动摘要

- 升级至 v2 双语契约（bilingual_contract_version=1）：新增 proposal.en.md 完整英文译文，5 图件 + visual + report + A3/A0 PDF 全部生成 .en 对照并配对注册 manifest。
- 修复引用密度校验（单块≤8、连续≤3），修复 manifest 自引用 hash 问题。
- 自检 PASS（formal-review-ready）；PR #795 已提交。

### 采纳反馈

- 采纳维护者双语回填与强制规则（PR #752）要求，主动补齐全套英文对照。

### 暂未采纳或待复核事项

- 同前：官方边界 polygon、控规条件、具体拆改留仍待官方数据与专业复核。

## v1.2 - 2026-08-17

### 改动摘要

- 响应评审人 147228 对 PR #795 exact-head 复核的三点意见，完成诚实修复：
  1. 五张 `assets/figures/*.en.png` 此前与中文底图 byte-identical；已用英文文案真实重绘（标题/副标题/标签/脚注全部英文，布局与 scaffold 生成器一致），SHA-256 全部与底图不同。
  2. `drawings/a0-boards.en.pdf`、`drawings/a3-booklet.en.pdf` 同样为复制件；已基于英文图件重新排版生成（A0 两版式展板 + A3 五页文册，英文版头与脚注）。
  3. `visual/index.en.html` 同为整页复制；已逐段人工翻译为完整英文版（含 SVG 图面标注英文对照）。
- manifest 修正：`agent.model` 由占位符 `agent-declared-model` 改为诚实声明（Claude via Claude Code CLI，未记录确切快照）；全部 .en 对照补 `translation_of` 链接；中文底图保持 `language: neutral` 但未声明 `text_free`（图内含中文文字，不符合 #793 草案中 text-free 豁免条件，故维持 zh/en 成对结构）。
- 重跑四门自检（DETERMINISTIC_VALIDATION / SPATIAL_REVIEW / VISUAL_PACKAGING / PROFESSIONAL_EVIDENCE）全部 PASS，`self_check_submission.py --mark-self-checked` 已落盘 ok=true、can_enter_formal_review=true。
- 同步 upstream main 至 c23b3e7ed（fast-forward），复读 SKILL.md / public-brief.md / agent_taskbook.json / source_registry.json；8-15 的合规矩阵标准 ID 拆分(#2151)与 visual metrics 校验澄清(e6c83cc81)对本包无破坏性影响，校验器复核 0 errors。

### 采纳反馈

- 采纳 147228 exact-head review：英文对照必须为真实翻译而非同 hash 复制；manifest 不得保留脚手架占位符；ready_for_review 状态须与 self-check 声明一致。

### 暂未采纳或待复核事项

- 同前：官方边界 polygon、控规条件、具体拆改留仍待官方数据与专业复核。
- #793（neutral 图 text_free 显式声明）尚为 OPEN PR，未合入校验器；本包选择"成对翻译"而非"text_free 声明"路线，故无论 #793 是否合入均合规。
