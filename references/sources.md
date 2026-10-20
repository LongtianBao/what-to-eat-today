# Evidence and design notes / 参考与设计取舍

核查日期：2026-10-19。以下是定向检索所得，非全网排名，也未运行第三方服务。流程独立撰写，不复制第三方指令。更新临床建议或实际接入服务时重新核实。

English note: these are design references, not a ranking or an integration claim. Instructions were written independently. Clinical links are starting points, last reviewed on the date above; verify applicable current primary guidance when using health adaptations. Runtime profiles and report details are excluded from this package.

## 现有 skill

| 项目 | 可借鉴部分 | 本 skill 的取舍 |
|---|---|---|
| [Recipe API weekly-meal-planner](https://github.com/recipe-api/claude-skills/blob/main/skills/weekly-meal-planner/SKILL.md) | 需求集中收集、食谱筛选、合并采购、按份计算 | 原文依赖 Recipe API connector；本机不假设可用，不依赖付费调用，增加体检和医嘱适用性核对 |
| [HaydenI OpenClaw Meal Planner](https://github.com/HaydenI/openclaw-meal-planner/blob/main/SKILL.md) | 库存、预算、历史菜单、批量备餐 | 本地资料移出可复用 skill；不采用自动删除历史规则，不默认补购所有常备品；采购工具按实际授权使用 |
| [SkillMedev Nutrition Planner](https://github.com/SkillMedev/skills/blob/main/skills/nutrition-planner/SKILL.md) | 目标与执行结构分离、按反馈降低复杂度 | 原文默认蛋白质 1.6–2.2 g/kg 及固定饮水框架，不能直接迁移到未知临床情况；本版本核实适用性后才设置目标 |
| [Gordon Ramsay Meal Planner](https://github.com/lazyfoxjumps/Gordon-Ramsay-Meal-Planner/blob/main/SKILL.md) | 重视实际烹饪、快捷餐和剩菜利用 | 不采用固定角色口吻；以用户语言和简洁执行说明输出 |

## 医学与食品安全主来源

- [AHA Diet and Lifestyle Recommendations](https://www.heart.org/en/healthy-living/healthy-eating/eat-smart/nutrition-basics/aha-diet-and-lifestyle-recommendations)：饮食结构、蔬果全谷、蛋白来源、脂肪替换、盐和添加糖。用于一般结构依据，不自动生成个人治疗目标。
- [NIDDK: Healthy Eating for Adults with CKD](https://www.niddk.nih.gov/health-information/kidney-disease/chronic-kidney-disease-ckd/healthy-eating-adults-chronic-kidney-disease)：蛋白、钾、磷和液体应结合病情与医疗团队；支持避免套用统一模板。
- [NIDDK: Healthy Living with Diabetes](https://www.niddk.nih.gov/health-information/diabetes/overview/healthy-living-with-diabetes)：个体化饮食与药物、活动的关系；部分降糖药使用者跳餐或延迟进餐会发生低血糖。
- [USDA FSIS: Leftovers and Food Safety](https://www.fsis.usda.gov/food-safety/safe-food-handling-and-preparation/food-safety-basics/leftovers-and-food-safety)：冷却、冷藏期限及复热。
- [USDA FoodData Central](https://fdc.nal.usda.gov/)：可用的食品营养数据入口。具体数字必须检索对应条目/标签；当前未连接 API，不能据此声称某份菜单营养已计算。

这些来源不覆盖每项体检异常。遇到新问题时按其适用人群和地区补查官方/专业指南，而不是将此列表当作通用治疗规则库。
- [FDA: Have Food Allergies? Read the Label](https://www.fda.gov/consumers/consumer-updates/have-food-allergies-read-label)：配料、过敏原声明及自愿的交叉接触警示；缺少预防性警示不等于无风险。

## 报告核对时补充的依据（2026-10-19）

- [MedlinePlus Calcium Blood Test](https://medlineplus.gov/lab-tests/calcium-blood-test/)：总钙、游离钙的区别及异常结果可能的多种原因；不直接按膳食缺钙处理。
- [MedlinePlus Chloride Blood Test](https://medlineplus.gov/lab-tests/chloride-blood-test/)：结果需结合其它检测、健康情况与药物解释；不直接以加盐纠正。
- [AHA 2026 Dietary Guidance](https://professional.heart.org/en/science-news/2026-dietary-guidance-to-improve-cardiovascular-health/top-things-to-know)：支持整体饮食结构和不饱和脂肪替换，个人治疗目标仍需核实。
