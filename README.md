# 今天吃啥 · What to Eat Today

按你的口味和生活方式，决定今天吃啥。

A bilingual meal-planning skill built around your tastes and everyday routine.

[中文说明](#中文说明) · [English guide](#english-guide)

## 中文说明

「今天吃啥」是面向 Codex 和 Claude Code 的食谱规划 skill。它可以安排今天一餐、一起做的午晚两餐，或一周菜单；按每个人的口味、时间、预算、厨具和已核实的饮食需求调整推荐。

### 能做什么

- **按口味选菜：** 分开记录喜欢的菜系、食材，以及辣、麻、酸、甜偏好。每个人有独立档案，不把某个人的喜好当作所有人的默认。
- **适配带饭与批量做饭：** 午晚餐一起做时，给出整锅用量和每盒分配；区分生重、熟重、带骨采购重量和可食部。
- **把计量写清楚：** 使用克和 mL，可同时注明标准量勺：1 茶匙＝5 mL、1 汤匙＝15 mL。普通餐勺和汤勺不默认有标准容量。
- **可选健康适配：** 根据用户提供的体检资料及医嘱落实已核实的饮食限制；区分检查结果、诊断和医嘱，说明关键缺口，不自行诊断或开补剂。
- **把菜单变成备餐安排：** 合并采购量、注明采购包装与结余，安排冷藏、冷冻、运输和复热，并区分计划、加购、购买和已吃。

### 安装与使用

这是一个文件夹形式的 skill，没有必须购买的食谱 API，也没有捆绑可执行代码。按使用的工具选择安装位置：

**Codex：**

```sh
git clone https://github.com/LongtianBao/what-to-eat-today.git ~/.codex/skills/what-to-eat-today
```

**Claude Code：**

```sh
git clone https://github.com/LongtianBao/what-to-eat-today.git ~/.claude/skills/what-to-eat-today
```

在 Codex 中使用 `$what-to-eat-today`，在 Claude Code 中使用 `/what-to-eat-today`。支持自动发现 skill 的环境也可以通过自然语言请求触发。若目标目录已存在，先检查再更新，避免覆盖私人文件；如未发现新 skill，可重新启动或重新加载工具。

示例：

> 用今天吃啥帮我规划今天的午晚餐。我喜欢川菜，两餐一起做，有鸡腿，主动操作不超过25分钟。

> 根据我的私人饮食档案，安排下周五天的带饭菜单。先核对还缺哪些健康信息，再给整锅用量和采购清单。

### 隐私与语言

中文和英文都有完整工作流程及健康约束说明。入口只加载本次需要的语言版本；涉及体检或医嘱时才加载健康规则。

私人资料默认保存在 `~/.local/share/what-to-eat-today/`，与 skill 和公开仓库分开；每个人使用独立档案。已有的本机 `weekly-meals` 私人档案仍可继续使用。本仓库不包含真实用户档案、体检报告、账号或饮食历史；上传报告到第三方服务前须获得针对资料和目的地的明确授权。

### 使用边界与许可

这是饮食规划辅助工具，不替代医学诊断或治疗，也不保证营养达标。执行前须核对医嘱、实际食品标签和储存条件。购物、发布等操作需要用户授权；规划不会自动下单、订阅或设置提醒。

参见[证据来源与设计取舍](references/sources.md)。本项目采用 [MIT 许可证](LICENSE)。

## English guide

What to Eat Today is a meal-planning skill for Codex and Claude Code. Plan one meal, a shared lunch-and-dinner batch, or a week of meals around each person's tastes, time, budget, equipment and verified dietary requirements.

### What it does

- **Choose dishes around individual tastes:** record preferred cuisines, ingredients, heat, numbing, sourness and sweetness separately. Each person has their own profile; one person's preferences never become everyone's defaults.
- **Support packed meals and batch cooking:** give whole-batch quantities and per-container portions when lunch and dinner are cooked together. Distinguish raw, cooked, bone-in purchasing and edible-portion weights.
- **Make measurements usable:** use grams and mL, optionally with standard measuring spoons: 1 tsp = 5 mL and 1 tbsp = 15 mL. Ordinary dining spoons and ladles have unknown capacity until verified.
- **Optionally adapt to health requirements:** apply verified dietary restrictions from user-provided reports and clinician instructions. Keep test results, diagnoses and clinical orders separate, identify critical missing information, and avoid independently diagnosing or prescribing supplements.
- **Turn menus into preparation plans:** combine grocery quantities, distinguish purchase packages from expected leftovers, and plan refrigeration, freezing, transport and reheating. Planned, added to cart, purchased and eaten are separate states.

### Install and use

This is a folder-based skill, with no required paid recipe API or bundled executable code. Choose the installation directory for your agent:

**Codex:**

```sh
git clone https://github.com/LongtianBao/what-to-eat-today.git ~/.codex/skills/what-to-eat-today
```

**Claude Code:**

```sh
git clone https://github.com/LongtianBao/what-to-eat-today.git ~/.claude/skills/what-to-eat-today
```

Use `$what-to-eat-today` in Codex or `/what-to-eat-today` in Claude Code. Natural meal-planning requests can also trigger the skill when automatic discovery is supported. If the target directory already exists, inspect it before updating to avoid overwriting personal files. Restart or reload the agent if the new skill is not discovered.

Examples:

> Use What to Eat Today to plan lunch and dinner. I like Sichuan food, cook both meals together, have chicken thighs, and can spend 25 minutes actively cooking.

> Use my private profile to plan five days of packed meals next week. Check which health details are still missing before giving whole-batch quantities and a grocery list.

### Privacy and language

Both Chinese and English have complete workflows and health guidance. The entrypoint loads only the language needed for the request; health rules are loaded when reports or clinician instructions are relevant.

Private data defaults to `~/.local/share/what-to-eat-today/`, outside the skill and public repository, with separate records for each person. Existing local `weekly-meals` profiles remain usable. This repository contains no real user profiles, medical reports, accounts or meal history. Uploading reports to a third-party service requires explicit authorization covering the data and destination.

### Scope and license

This skill supports meal planning; it does not replace medical diagnosis or treatment or guarantee nutritional adequacy. Verify clinician instructions, actual food labels and storage conditions before use. Shopping and publishing require user authorization; planning does not automatically place orders, start subscriptions or set reminders.

See the [evidence and design notes](references/sources.md). Licensed under the [MIT License](LICENSE).
