# Installing Hall of Fame for Codex

Enable hall-of-fame skills in Codex via native skill discovery. Just clone and symlink.

## Prerequisites

- Git
- Codex CLI installed

## Installation

1. **Clone the hall-of-fame repository:**
   ```bash
   git clone https://github.com/konglong87/hall-of-fame.git ~/.codex/hall-of-fame
   ```

2. **Create the skills symlink:**
   ```bash
   mkdir -p ~/.agents/skills
   ln -s ~/.codex/hall-of-fame ~/.agents/skills/hall-of-fame
   ```

   **Windows (PowerShell):**
   ```powershell
   New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills"
   cmd /c mklink /J "$env:USERPROFILE\.agents\skills\hall-of-fame" "$env:USERPROFILE\.codex\hall-of-fame"
   ```

3. **Restart Codex** (quit and relaunch the CLI) to discover the skills.

## Verify

```bash
ls -la ~/.agents/skills/hall-of-fame
```

You should see a symlink (or junction on Windows) pointing to your hall-of-fame directory.

## Available Skills

After installation, you'll have access to the **hall-of-fame** skill:

- **hall-of-fame** - 名人堂专家集合，聚合13位顶尖专家思维框架
  - 智能路由系统（关键词匹配+LLM分类）
  - 动态加载专家SKILL.md，避免context污染
  - SessionStart Hook自动注入skill介绍
  - 覆盖教育升学、产品增长、创业商业、投资财富、思维学习、写作思考、传统智慧、法理正义等多个领域

## Usage

Skills are automatically triggered based on your requests. For example:

```
用户：高考选专业，计算机和金融哪个就业前景更好
AI: [自动路由到张雪峰]

用户：我的产品用户增长停滞，怎么突破
AI: [自动路由到张一鸣]

用户：YouTube视频CTR怎么提升到10%
AI: [自动路由到MrBeast]

用户：我想创业，但不知道做什么方向
AI: [自动路由到Paul Graham]

用户：这个投资决策有没有认知偏误
AI: [自动路由到查理·芒格]

用户：怎么建立无需许可的财富创造系统
AI: [自动路由到Naval]

用户：怎么验证自己真的理解了一个概念
AI: [自动路由到费曼]

用户：这个风险评估有没有脆弱性
AI: [自动路由到塔勒布]

用户：怎么写出有趣又有深度的文章
AI: [自动路由到王小波]

用户：在逆境中怎么保持心态
AI: [自动路由到郭德纲]

用户：张三这种情况算正当防卫吗
AI: [自动路由到罗翔]
```

## Available Experts

| 专家 | 专业领域 | 核心方法论 | 适用场景 |
|------|---------|-----------|---------|
| 张雪峰 | 教育升学 | 社会筛子论、就业倒推法 | 高考选专业、考研院校 |
| 张一鸣 | 产品增长 | 延迟满足感、Context not Control | 产品策略、推荐算法 |
| MrBeast | 内容创作 | CTR×AVD方程式、零无聊时刻 | YouTube视频优化 |
| 乔布斯 | 产品设计 | 聚焦即说不、端到端控制 | 设计美学、用户体验 |
| Paul Graham | 创业通用 | Writing=Thinking、Superlinear Returns | 创业方向、创始人评估 |
| 马斯克 | 技术创业 | 第一性原理、渐近极限法 | 成本拆解、垂直整合 |
| 查理·芒格 | 投资决策 | 多元思维模型、逆向思考 | 认知偏误检测、决策审视 |
| Naval | 财富创造 | 杠杆思维、特定知识 | 财富路径、欲望管理 |
| 费曼 | 思维学习 | 命名≠理解、反自欺原则 | 概念理解、学习方法 |
| 塔勒布 | 风险应对 | 反脆弱思维、黑天鹅应对 | 不确定性、风险评估 |
| 王小波 | 写作思考 | 理性+自由+有趣、荒谬解剖 | 独立思考、写作反讽 |
| 郭德纲 | 传统智慧 | 手艺人哲学、人情世故 | 传统艺术、逆境应对 |
| 罗翔 | 法理正义 | 圆圈正义、刑法思维 | 法律问题、正义哲学 |

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
cd ~/.codex/hall-of-fame && git pull
```

Skills update instantly through the symlink.

## Uninstalling

```bash
rm ~/.agents/skills/hall-of-fame
```

Optionally delete the clone: `rm -rf ~/.codex/hall-of-fame`.

## Support

- **Issues**: https://github.com/konglong87/hall-of-fame/issues
- **Documentation**: https://github.com/konglong87/hall-of-fame/blob/main/README.md