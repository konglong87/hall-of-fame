# Installing Hall of Fame for OpenCode

## Prerequisites

- [OpenCode.ai](https://opencode.ai) installed
- Git installed

## Installation Steps

### 1. Clone Hall of Fame

```bash
git clone https://github.com/konglong87/hall-of-fame.git ~/.config/opencode/hall-of-fame
```

### 2. Register the Plugin

Create a symlink so OpenCode discovers the plugin:

```bash
mkdir -p ~/.config/opencode/plugins
rm -f ~/.config/opencode/plugins/hall-of-fame.js
ln -s ~/.config/opencode/hall-of-fame/.opencode/plugins/hall-of-fame.js ~/.config/opencode/plugins/hall-of-fame.js
```

### 3. Symlink Skills

Create a symlink so OpenCode's native skill tool discovers hall-of-fame:

```bash
mkdir -p ~/.config/opencode/skills
rm -rf ~/.config/opencode/skills/hall-of-fame
ln -s ~/.config/opencode/hall-of-fame ~/.config/opencode/skills/hall-of-fame
```

### 4. Restart OpenCode

Restart OpenCode to discover the skills.

Verify by asking: "你有哪些名人堂专家技能？"

## Usage

### Finding Skills

Use OpenCode's native `skill` tool to list available skills:

```
use skill tool to list skills
```

### Loading a Skill

Use OpenCode's native `skill` tool to load the hall-of-fame skill:

```
use skill tool to load hall-of-fame/hall-of-fame
```

### Skill Triggers

The hall-of-fame skill automatically triggers when:
- User mentions: '高考', '专业', '产品', '增长', '创业', '投资', '风险', '写作', '法律', '相声'
- User asks for expert perspective or advice
- User describes a decision-making scenario

### Example Interactions

```
用户：高考选专业，计算机和金融哪个就业前景更好
AI: [自动触发 hall-of-fame，路由到张雪峰]
⚠️ 专家视角提醒
您已激活 张雪峰 视角。
本专家框架基于公开信息提炼，非本人观点。

[张雪峰的回答...]

用户：我的产品用户增长停滞，怎么突破
AI: [自动触发 hall-of-fame，路由到张一鸣]
⚠️ 专家视角提醒
您已激活 张一鸣 视角。

[张一鸣的回答...]

用户：YouTube视频CTR怎么提升到10%
AI: [自动触发 hall-of-fame，路由到MrBeast]
⚠️ 专家视角提醒
您已激活 MrBeast 视角。

[MrBeast的回答...]

用户：我想创业，但不知道做什么方向
AI: [自动触发 hall-of-fame，路由到Paul Graham]
⚠️ 专家视角提醒
您已激活 Paul Graham 视角。

[Paul Graham的回答...]

用户：这个投资决策有没有认知偏误
AI: [自动触发 hall-of-fame，路由到查理·芒格]
⚠️ 专家视角提醒
您已激活 查理·芒格 视角。

[芒格的回答...]

用户：怎么建立无需许可的财富创造系统
AI: [自动触发 hall-of-fame，路由到Naval]
⚠️ 专家视角提醒
您已激活 Naval 视角。

[Naval的回答...]

用户：怎么验证自己真的理解了一个概念
AI: [自动触发 hall-of-fame，路由到费曼]
⚠️ 专家视角提醒
您已激活 费曼 视角。

[费曼的回答...]

用户：这个风险评估有没有脆弱性
AI: [自动触发 hall-of-fame，路由到塔勒布]
⚠️ 专家视角提醒
您已激活 塔勒布 视角。

[塔勒布的回答...]

用户：怎么写出有趣又有深度的文章
AI: [自动触发 hall-of-fame，路由到王小波]
⚠️ 专家视角提醒
您已激活 王小波 视角。

[王小波的回答...]

用户：在逆境中怎么保持心态
AI: [自动触发 hall-of-fame，路由到郭德纲]
⚠️ 专家视角提醒
您已激活 郭德纲 视角。

[郭德纲的回答...]

用户：张三这种情况算正当防卫吗
AI: [自动触发 hall-of-fame，路由到罗翔]
⚠️ 专家视角提醒
您已激活 罗翔 视角。

[罗翔的回答...]
```

### Available Experts

- **张雪峰** - 教育升学专家，就业数据导向
  - 社会筛子论、就业倒推法、阶层现实主义、中位数原则
  - 适用场景：高考志愿填报、专业选择、考研院校

- **张一鸣** - 产品增长策略，组织管理经验
  - 延迟满足感、Context not Control、逃逸平庸的重力、网络效应飞轮
  - 适用场景：产品策略、推荐算法、组织管理、全球化决策

- **MrBeast** - YouTube方法论、CTR优化实战
  - CTR×AVD方程式、零无聊时刻、阶梯递进、简单概念×极端执行
  - 适用场景：YouTube视频优化、标题封面设计、CTR提升

- **乔布斯** - 极简主义、端到端体验控制
  - 聚焦即说不、端到端控制、连点成线、死亡过滤器
  - 适用场景：产品设计美学、用户体验优化、创新方法论

- **Paul Graham** - YC经验、早期投资洞察
  - Writing=Thinking、Taste as Cognitive Instrument、Iterative Discovery、Superlinear Returns
  - 适用场景：创业方向选择、创业想法验证、创始人评估

- **马斯克** - 第一性原理、激进迭代
  - 渐近极限法、五步算法、存在主义锚定、垂直整合即物理必然
  - 适用场景：技术硬核创业、成本结构拆解、第一性原理应用

- **查理·芒格** - 认知偏误检测、逆向思考
  - 多元思维模型、逆向思考、Lollapalooza效应、能力圈+意见资格制
  - 适用场景：投资决策审视、认知偏误检测、决策盲点识别

- **Naval** - 杠杆策略、特定知识框架
  - 杠杆思维（劳动/资本/代码/媒体）、特定知识、欲望即合同、重新定义术
  - 适用场景：财富路径设计、杠杆策略选择、特定知识识别

- **费曼** - 科学思维、反自欺原则
  - 命名≠理解、反自欺原则、不确定性是力量、具象化思考
  - 适用场景：概念理解验证、学习方法优化、货物崇拜检测

- **塔勒布** - 反脆弱思维、不确定性应对
  - 反脆弱思维、黑天鹅应对、杠铃策略、幸存者偏差识别
  - 适用场景：风险评估决策、不确定性应对、反脆弱设计

- **王小波** - 理性写作、独立思考、对抗荒谬
  - 理性+自由+有趣、效率算法、话语功能解剖、举证责任逻辑
  - 适用场景：独立思考、写作反讽、对抗荒谬、逻辑分析

- **郭德纲** - 传统艺术智慧、人情世故应对
  - 手艺人哲学、控制权即安全感、观众即上帝、江湖规矩
  - 适用场景：传统艺术、逆境应对、人情世故、团队管理

- **罗翔** - 刑法思维、正义哲学、法理分析
  - 圆圈正义、刑法思维、法理分析、正义哲学
  - 适用场景：法律问题、正义哲学、法理分析、普法教育

### Personal Skills

Create your own skills in `~/.config/opencode/skills/`:

```bash
mkdir -p ~/.config/opencode/skills/my-skill
```

Create `~/.config/opencode/skills/my-skill/SKILL.md`:

```markdown
---
name: my-skill
description: Use when [condition] - [what it does]
---

# My Skill

[Your skill content here]
```

### Project Skills

Create project-specific skills in `.opencode/skills/` within your project.

**Skill Priority:** Project skills > Personal skills > Hall-of-fame skill

## Routing Mechanism

**双层路由策略：**

1. **关键词匹配（第一层）**
   - 扫描用户问题关键词
   - 计算匹配置信度 = 匹配关键词数 / 该类别关键词总数
   - 置信度 >= threshold → 直接路由

2. **LLM分类（第二层）**
   - 置信度不足时触发
   - 使用Claude进行分类判断
   - Fallback到Paul Graham

**多专家场景处理：**
- 产品+增长 → 检查"视频"关键词 → MrBeast或张一鸣
- 创业 → 检查"成本/技术"关键词 → 马斯克或Paul Graham

## Updating

```bash
cd ~/.config/opencode/hall-of-fame
git pull
```

## Troubleshooting

### Skills not found

1. Check skills symlink: `ls -l ~/.config/opencode/skills/hall-of-fame`
2. Verify it points to: `~/.config/opencode/hall-of-fame`
3. Use `skill` tool to list what's discovered
4. Restart OpenCode if skills don't appear

### Tool mapping

When skills reference Claude Code tools:
- `TodoWrite` → `todowrite`
- `Task` with subagents → `@mention` syntax
- `Skill` tool → OpenCode's native `skill` tool
- File operations → your native tools

## Getting Help

- Report issues: https://github.com/konglong87/hall-of-fame/issues
- Full documentation: https://github.com/konglong87/hall-of-fame/blob/main/README.md