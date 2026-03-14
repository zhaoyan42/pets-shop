---
stepsCompleted: [1, 2, 3, 4, 5, 6, 7]
inputDocuments:
  - "/Users/zhaoyanlong/Projects/pets-shop/_bmad-output/planning-artifacts/prd.md"
  - "/Users/zhaoyanlong/Projects/pets-shop/_bmad-output/brainstorming/brainstorming-session-2026-03-11-161500.md"
---

# UX Design Specification pets-shop

**Author:** Zhaoyanlong
**Date:** 2026-03-11

---

<!-- UX design content will be appended sequentially through collaborative workflow steps -->

## Executive Summary

### Project Vision
**pets-shop** 旨在通过数字化手段放大独立宠物店的“人情味”与“透明专业度”，作为一个“数字化合伙人”，致力于提升 10% 的客户复购率，并在店主、店员与客户之间建立深厚的情感信任闭环。

### Target Users
*   **独立店主**：追求经营科学化，通过客观报表（满意度、复购率、现金流）替代主观感觉进行决策。
*   **店员执行者**：厌恶被“事无巨细”地监工，需要易操作、低门槛（大按钮、语音）的移动端工具来记录专业表现并获得荣誉感。
*   **宠物主人**：渴望见证宠物成长，需要无感的预约体验和高分享价值的爱护记录。

### Key Design Challenges
*   **无感录入挑战**：在湿手、忙碌的工作环境下，通过极简交互生成高质量的情感记录。
*   **和谐管理的视觉去压力化**：实现管理透明度（荣誉墙、实时负荷）的同时，保护员工隐私，规避内卷和受挫感。
*   **多端实时同步的响应感**：基于 WebSocket 的评价流与排队动态更新需具备直观且温和的视觉反馈。

### Design Opportunities
*   **情感化社交资产**：将常规服务转化为“爱宠成长日记”，通过高颜值、易分享的卡片式设计驱动口碑传播。
*   **自组织协作看板**：通过视觉化的“负荷天平”，引导店员在无店主干预的情况下自发完成任务补位与插队处理。

## Core User Experience

### Defining Experience
本系统的核心体验是“信任的情感化闭环”。通过**粘土拟态 (Claymorphism)** 设计语言，将枯燥的店内管理转化为具有“实感”和“温度”的生命见证过程。

### Platform Strategy
- **WeChat Mini Program (Mobile)**: 
    - **Eyes-Free Friendly (盲操兼容)**: 核心交互热区占据屏幕中下部 60% 面积，支持“长按确认”与“手势切换”，适配店员湿手、无需注视的操作场景。
    - **多端同步**: 利用 WebSocket 实现任务流的“果冻式”动画平滑更新。
- **Web Dashboard (Desktop)**: 
    - **经营驾驶舱**: 提供高对比度、信息密集的图表交互，侧重现金流预警、复购率分析及经营实验复盘。

### Effortless Interactions
- **软压点击反馈**: 所有粘土风格按钮提供 200ms ease-out 的物理塌陷动效，增强交互的“实感”。
- **全屏即触发**: 工单模式下，屏幕中下部为巨大粘土圆环触控区。**短按拍照/录音，长按 1 秒完成阶段任务**，配合触觉震动反馈。
- **语义化信息流**: 语音录入通过 NLP 自动转化为结构化标签，店员无需手动点击分类。

### Experience Principles
- **粘土化设计 (Claymorphism)**: 大圆角 (16-24px) + 双重阴影，主色调活力橙 (#F97316)，营造温暖、亲和的品牌初印象。
- **荣誉驱动透明度**: 评价反馈以“笑脸飘过”等轻量化动效呈现；荣誉墙仅展示前 20%，侧重正向激励。
- **反馈即资产**: 保留客户原始笔触，将每一次服务反馈沉淀为可分享的“爱心日记”卡片。

## Desired Emotional Response

### Primary Emotional Goals
- **店员：【自豪与掌控】**。通过触觉确认和荣誉激励，将“任务”转化为“专业成就”。
- **客户：【安心与被宠溺】**。通过拟人化的状态更新和成长记录，建立极高依赖度。
- **店主：【全局掌控的宁静】**。通过客观、实时的数据看板消除管理焦虑。

### Emotional Journey Mapping
- **初次打开**：温润治愈（粘土拟态视觉）。
- **操作反馈**：物理确认感（软压动效 + 微信原生触觉震动反馈 `wx.vibrateShort`）。
- **被插队/等待**：被体谅、参与公益感（粘土宠物求助动画 + “爱心守护”勋章）。
- **服务结项**：惊喜与分享欲（通过 Canvas 渲染带店员手写笔迹的高颜值海报）。

### Design Implications (WeChat Expert Principles)
- **触觉补偿 (Haptic Confirmation)**: 仅在“任务结项”或“安全预警”等关键节点触发 `wx.vibrateShort`，建立物理级的信任。
- **交互行为驱动授权 (Driver Authorization)**: 将订阅消息授权按钮隐藏在“查看爱宠瞬间”等爽点操作中，实现无感、高转化率的触达。
- **人格化通知 (Persona Notifications)**: 所有系统通知采用“宠物视角”或“关怀语调”，杜绝机器感。

## UX Pattern Analysis & Inspiration

### Inspiring Products Analysis
- **iOS 灵动岛 (Dynamic Island)**: 用于店员端全局状态常驻，实现任务进度的无感监控与极速切换。
- **小红书 (Xiaohongshu)**: 提供“叙事性内容”组织灵感，将碎片化的服务记录转化为高颜值的“故事卡片”。
- **多邻国 (Duolingo)**: 引入“复购连胜 (Grooming Streak)”逻辑，将周期性服务博弈化，提升粘性。

### Transferable UX Patterns
- **【任务灵动胶囊】**: 店员端顶部常驻，实时显示当前服务宠物的倒计时与关键标记，支持点击展开微型控制台。
- **【瀑布流宠物志】**: 客户侧采用非线性网格，按时间轴沉淀宠物的成长瞬间，弱化订单感。
- **【非线性果冻动效】**: 用于所有状态变更（如排队移动），模拟物理世界的柔性碰撞，缓解用户焦虑。

### Design Inspiration Strategy
- **Adopt (采用)**: 灵动岛任务管理、小红书社交化海报、手写体笔迹渲染。
- **Adapt (适配)**: 将叮咚买菜的库存预警适配为独立店的“现金流预警”视觉模型。
- **Avoid (规避)**: 彻底规避深层级菜单导航与强制文字录入框。

## Design System Foundation

### 1.1 Design System Choice
**Themeable Atomic System (UnoCSS/Tailwind for Mini Program)**：一种基于原子化 CSS 思想、专为小程序环境优化的半定制化粘土拟态系统。

### Rationale for Selection
- **多端一致性**: 通过 JSON 格式的“设计令牌 (Design Tokens)”实现 Web 端与小程序端的视觉基因同步。
- **性能与降级**: 编译时生成 WXSS，体积轻量，且天然支持低端设备的“视觉降级”方案。
- **组件化触感**: 将震动反馈与粘土动效封装在底层组件中，确保“盲操级”交互在全局范围内的一致性。

### Implementation Approach
- **核心令牌库**: 定义 `Rounded-Clay`, `Shadow-Inner`, `Shadow-Outer` 及 `Color-Brand-Orange` 等原子类。
- **全局组件集 (Clay-UI)**: 包含内置震动反馈的 `ClayButton`、动态阴影的 `ClayCard` 以及支持长按逻辑的 `TriggerRing`。

### Customization Strategy
- **场景自适应**: 店员/客户移动端维持“重粘土”感（提升情感温度）；店主 Web 端降级为“轻粘土”风格（提升数据阅读效率）。
- **品牌预留**: 颜色与圆角参数均通过 Token 暴露，支持未来快速调整品牌色。

## 2. Core User Experience Detail

### 2.1 Defining Experience
**“捕捉并分享爱宠的瞬间”**：这是连接店员专业执行与客户情感见证的核心纽带。通过极简的物理化交互（灵动胶囊 + 触发圆环），让“记录”本身成为服务的一部分，而非负担。

### 2.2 User Mental Model
- **店员模型**：“我不必低头看手机，只需按一下（或说话），系统就懂我。”——将复杂的工单流程简化为物理直觉。
- **客户模型**：“这不是在看订单，这是在看我的爱宠在‘幼儿园’的精彩表现。”——将交易感转化为成长叙事。

### 2.3 Success Criteria
- **5 秒准则**：店员从决定拍照到完成上传的总时长控制在 5 秒内。
- **30 分钟分享回响**：高质量海报驱动客户分享后，预期 30 分钟内获得社交圈互动。
- **零焦虑排队**：发生插队调整时，通过非线性动效和温情补偿，使客户投诉率保持为零。

### 2.4 Novel UX Patterns
- **粘土灵动胶囊 (Task Capsule)**：借鉴灵动岛，作为全局任务控制器，在任意页面提供状态回响。
- **全屏触发圆环 (Action Ring)**：工单页核心交互，支持盲操级的长按与短按识别。

### 2.5 Experience Mechanics
1. **引导**：顶部任务胶囊呈脉冲跳动状态，提示当前关键动作（如：该吹干了）。
2. **执行**：店员在大拇指热区点击/长按圆环，完成动作。
3. **反馈**：物理级震动 + 粘土按钮塌陷动效，配合“确认音效”。
4. **结项**：系统自动触发订阅消息，并渲染手写感卡片，进入客户时间轴。
