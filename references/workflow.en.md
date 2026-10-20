# Meal planning workflow

## Reuse a private profile

Default private directory: `~/.local/share/what-to-eat-today/`. Use the user's configured directory first. An existing `~/.local/share/weekly-meals/` is a legacy location: continue using it for the same confirmed person instead of silently starting over or copying private files into the skill. Read `profile.json`, relevant `health-records.json` when needed, and only recent relevant plans in `plans/`.

For another person, use a separate directory such as `profiles/<person-id>/`. Establish who the plan is for before using health records. For shared meals, satisfy the intersection of allergies and medical restrictions, then separate sauces or sides to accommodate tastes. Missing information means unknown.

Reuse confirmed facts; collect the gaps that materially affect this request in one short question. For health-adapted, ready-to-cook recommendations, confirm allergies, relevant medicines/supplements, and clinician dietary restrictions. While safety-critical answers are pending, provide an explicitly provisional example or work on schedules and equipment; do not claim clinical suitability. Optional gaps such as inventory or spice preference need not block a lifestyle draft. Never repeatedly ask about answered fields.

Relevant profile fields: preferred cuisines and dishes; disliked ingredients; heat, numbing, sourness and sweetness separately; allergies; clinician restrictions and dates; goals; people and meals covered; budget/currency; cooking time; equipment; refrigeration/reheating access; cooking frequency and batch size. Obtain age, relevant physiology, size and activity only when needed for applicable numerical targets. Keep explicit preferences active, inferences tentative, and one-off dishes scoped to that meal.

## Choose the requested scope

- **Today / one dish:** use available ingredients, give the requested recipe and useful substitutions. A question about chicken does not require generating seven days.
- **Packed lunch / batch:** establish which meals share a cooking batch and the cooking time. Two meals cooked together do not imply two separate cooking sessions or permission to repeat the same dish all week.
- **Weekly:** date the plan, cover the requested meals, reuse ingredients and schedule quick options for busy days. Read only relevant calendar information if that access is authorized.

Taste drives dish selection. Filter safety constraints first, then rank by actual preferences, cost, time and availability, and balance variety. Cuisine names do not determine spice tolerance, oil/salt preference, or acceptance of every ingredient. Preserve the defining flavors of a dish while explaining necessary changes. Keep chili/pepper flavor distinct from oil/salt quantity. Do not default to weight loss, fasting, high protein, supplements, or a single cuisine for every user.

## Make quantities usable

For every recipe, state people, portions and meals. Label weights as raw/cooked and edible portion; distinguish bone-in purchasing weight from boneless meat. Give ingredients for the **whole batch**, then allocation per meal/container. Count oil, soy sauce and other seasonings once for the whole batch. Scale the recipe explicitly when the meal count changes; adjust reduction, pan size and cooking time as needed rather than mechanically doubling everything.

Use grams and mL with optional standard spoon equivalents: **1 tsp = 5 mL; 1 tbsp = 15 mL** as this skill's recipe convention. If a local measuring set uses another convention, use its labeled mL. Distinguish volume from mass: 5 mL salt is not 5 g salt; conversions need a reliable ingredient-specific source. Dry spoonfuls are level; liquid spoonfuls reach the rim. Ordinary dining spoons, ladles, bottle pumps and sprays have unknown volume until labeled or measured; utensil weight and length do not establish capacity.

Match the user's cooking workflow and equipment aesthetics when kitchen tools are requested. Examples include resident spoons in lidded condiment pots, portable lunch containers, handled cooking-oil pots, or table cruets. Verify mL, dimensions, lid clearance and material on actual listings. Included serving spoons have unknown capacity unless specified. A product marketed for olive oil may hold other edible oils when its material and construction are suitable; choose the form the user wants. Do not add unrequested equipment to a food shopping list.

For each meal give dish, portions, practical steps, active/total time and a flavor-compatible fallback. Nutrition numbers need a matching label, verified recipe or database entry with serving basis and uncertainty. Without data, give a qualitative check. A dinner-only plan cannot establish full-day adequacy.

## Shop, pack and learn

Merge grocery quantities across recipes; subtract only confirmed usable stock. Separate recipe consumption from purchase package sizes and expected leftovers. Include counted seasonings. Organize by produce, proteins, starches, dairy/alternatives and condiments. State store/date for checked prices, or mark rough estimates. Keep budget/currency explicit.

Plan cooling, refrigeration/freezing, transport, thawing and reheating. For packed meals, check workplace refrigeration, insulated transport and reheating access rather than assuming food can sit out until lunch. Use the storage limits in health rules and check food-specific exceptions. Avoid putting a whole week of cooked meals in the refrigerator by default.

Shopping list → cart → purchase are separate authorized actions. Keep unrelated cart items unchanged unless included by the user. Before ordering, verify variants, quantities, existing duplicates, address/payment selection and total including tax, shipping and mandatory fees against the user's authorized budget. After an uncertain submission, inspect the order status before any retry. Record purchased only after visible order confirmation; a purchase does not prove consumption or medication use.

Save plans privately as `plans/YYYY-MM-DD.md` using the relevant day's date or week start. Preserve earlier versions on revision. Give a concise chat summary and file link. Distinguish planned, ordered and eaten; update actual intake only from user reports. Check meal coverage, allergy/restriction compatibility, taste, portion and shopping arithmetic, time, storage, and unresolved gaps before calling a plan ready. Learn specific feedback for future meals, without turning a single purchase or dish into a universal preference. Weekly planning does not set reminders automatically.
