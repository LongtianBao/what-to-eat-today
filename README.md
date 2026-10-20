# 今天吃啥 · What to Eat Today

A bilingual agent skill for the daily question: **what should I cook today?**

[中文](#中文) · [English](#english)

## 中文

按每个人的口味、时间、预算、带饭方式和已核实的饮食需求，规划今天一餐、午晚两餐或一周菜单。

- **口味是输入：** 分开记录菜系、食材、辣麻酸甜；不把一个人的喜好当作通用默认。
- **照顾真实做饭方式：** 午晚餐一起做时，给整锅用量和每盒分配；支持生熟/带骨重量、5 mL 茶匙与15 mL 汤匙。
- **可选体检适配：** 保留报告出处和医嘱区别；缺少关键安全信息时说明缺口，不自行诊断或开补剂。
- **从菜单到带饭：** 合并采购、包装结余、冷藏冷冻、运输复热，并区分计划、加购、购买与已吃。
- **私人资料留在本机：** 本仓库没有用户档案、体检报告、账户或真实饮食历史。支持每个人独立目录。

试着说：

> 今天吃啥？我喜欢川菜，午饭和晚饭一起做，有鸡腿，主动操作不超过25分钟。

> 用我的私人饮食档案安排下周五天的带饭菜单，先核对还缺哪些健康信息。

## English

Plan one meal, a shared lunch/dinner batch, or a week around individual tastes, time, budget, equipment and verified dietary requirements.

Taste affects dish selection. Batch quantities remain separate from per-meal portions. Optional health adaptation keeps report evidence separate from diagnoses and clinician instructions. Grocery math, transport and storage make the plan usable. Private profiles and medical reports stay outside the repository and the skill; each person gets separate records.

Try:

> What should I cook today? I like Sichuan food, cook lunch and dinner together, have chicken thighs, and can spend 25 minutes actively cooking.

> Use my private profile for five packed lunches next week. Check which health details are still missing first.

## Install / 安装

This is a folder-based skill, with no required paid recipe API or bundled executable code. Install for either agent by cloning into its skill directory:

```sh
# Codex
 git clone https://github.com/LongtianBao/what-to-eat-today.git ~/.codex/skills/what-to-eat-today

# OR Claude Code / 或安装到 Claude Code
 git clone https://github.com/LongtianBao/what-to-eat-today.git ~/.claude/skills/what-to-eat-today
```

Use `$what-to-eat-today` in Codex or `/what-to-eat-today` in Claude Code; natural meal-planning requests can also select it when automatic skill discovery is supported. If a target folder exists, inspect it before updating; do not overwrite personal files. Restart/reload the agent if necessary for discovery.

The entrypoint loads only the requested language's workflow. Health guidance is loaded only when relevant. Existing local `weekly-meals` profiles remain usable; the new default is `~/.local/share/what-to-eat-today/`.

## Scope / 边界

Meal planning support, not medical diagnosis, treatment or a guarantee of nutritional adequacy. Verify current clinical advice and actual food labels. Shopping and posting require the user's authorization; no automatic orders, subscriptions or reminders.

说明性的食谱规划工具，不替代诊断和治疗。实际执行须核对医嘱、标签与储存条件；不会自动购物、发布或设置提醒。

See [evidence and design notes](references/sources.md). MIT licensed.
