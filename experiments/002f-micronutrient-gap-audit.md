# Experiment 002F: Micronutrient Gap Audit

**Date:** 2026-09-07  
**Status:** R&D audit of Prototype 002E

## Question

Given the current 002E formula, which micronutrients are actually weak once the whole day is totaled?

This uses generic Health Canada / USDA / NIH food-composition values and the current 002E quantities. Exact prototype numbers should be recalculated from the labels of the products actually purchased.

The reference frame here is an adult male in the 19–50 range. The key reference values are roughly:

- calcium: 1,000 mg/day
- magnesium: 400–420 mg/day
- potassium: 3,400 mg/day
- zinc: 11 mg/day
- selenium: 55 µg/day
- choline: 550 mg/day
- vitamin E: 15 mg/day
- folate: 400 µg DFE/day
- vitamin B12: 2.4 µg/day
- iodine: 150 µg/day

## 002E audited core

The audited formula is the 002E core before choosing the ~400 kcal carbohydrate slider:

- enriched dry pasta — 200 g
- ground pork — 150 g raw
- textured soy granules — 25 g dry
- red lentils — 20 g dry
- tomato concentrate — 80 g
- cooked/frozen spinach — 50 g
- frozen peas — 100 g
- red sweet pepper — 60 g
- mozzarella — 60 g
- sunflower oil — ~15 mL
- canola oil — ~15 mL
- margarine — 10 g
- extra-virgin olive oil — 5 g
- eggs — 2
- whole milk — 500 mL
- banana — 150 g
- frozen blueberries — 75 g
- natural peanut butter — 30 g
- ground flax — 10 g

## Approximate result

Planning estimate from generic food-composition data:

| Nutrient | 002E core estimate | Reference | Read |
| --- | ---: | ---: | --- |
| Calcium | ~1,250–1,300 mg | 1,000 mg | covered |
| Magnesium | ~500–550 mg | 400–420 mg | covered |
| Potassium | ~4,300–4,700 mg | 3,400 mg | covered |
| Zinc | ~14–16 mg | 11 mg | covered |
| Selenium | ~180–250 µg | 55 µg | strongly covered |
| Choline | ~650–725 mg | 550 mg | covered |
| Vitamin E | ~17–20 mg | 15 mg | covered |
| Folate | ~800–950+ µg DFE | 400 µg DFE | strongly covered |
| Vitamin B12 | ~4.5–5.0 µg | 2.4 µg | covered |
| Iodine | intentionally unspecified until salt dose is fixed | 150 µg | easy plug |
| EPA + DHA | only ~trace / ~60 mg from ordinary eggs and dairy | no Canadian RDA; 250 mg/day is a useful adult reference | clear gap on fish-free days |

## The funny result

There is no broad micronutrient crisis here.

The meal is already carrying most of the difficult minerals and vitamins through ordinary high-throughput foods:

- milk + mozzarella dominate calcium
- pasta + soy/lentils + peanut butter + spinach carry magnesium
- tomato concentrate + banana + milk + soy + spinach carry potassium
- pork + dairy + eggs + pasta carry zinc
- pasta + pork + eggs + dairy make selenium almost impossible to miss
- eggs are the choline anchor, with pork + milk + soy/peas filling the rest
- sunflower/canola oil + peanut butter + eggs cover vitamin E
- enriched pasta + spinach + lentils + peas + peanut butter cover folate
- milk + eggs + pork + mozzarella cover B12

The recipe can therefore be simplified later without immediately destroying micronutrient coverage.

## Iodine: specify the damn salt

Canadian table/general-household salt is required to contain **0.01% potassium iodide**. Health Canada also cites roughly **380 µg iodine per teaspoon** of household iodized salt.

Practical R&D rule:

- target about **2 g iodized table salt across the day** as the iodine plug, then verify the purchased brand
- that quantity alone is in the neighborhood of the 150 µg/day iodine target
- dairy and eggs may contribute additional iodine, but their iodine content is variable enough that the design should not rely on it

This also means the seasoning system can do real nutritional work while making the pasta taste better.

## EPA/DHA: the one real gap

Flax supplies ALA, but the current fish-free 002E day contains very little preformed EPA/DHA.

Health Canada lists approximately:

- Atlantic sardines, 106 g can: **0.54 g DHA + 0.50 g EPA = ~1.04 g EPA+DHA**
- Pacific sardines in tomato, 106 g can: **0.92 g DHA + 0.56 g EPA = ~1.48 g EPA+DHA**
- Atlantic mackerel, cooked, 75 g: **0.52 g DHA + 0.38 g EPA = ~0.90 g EPA+DHA**

A useful adult reference is roughly **250 mg/day EPA+DHA**, or about **1.75 g/week**.

That makes the cleanest fix hilariously small:

### Fish module

Eat **2 sardine cans or ~2 mackerel servings per week**.

Two Atlantic sardine cans already provide about **2.08 g EPA+DHA/week**, averaging ~300 mg/day across the week. Two Pacific cans average ~420 mg/day.

Three fish servings per week is fine if it is enjoyable, but the arithmetic does not force daily fish.

## Selenium warning: do not add Brazil nuts for optimization points

The core already appears selenium-rich because grains, pork, eggs and dairy all contribute.

Brazil nuts would solve a problem that does not exist and make selenium harder to control. Keep them as food if desired, not as a micronutrient patch for this recipe.

## Vitamin E survived the audit

The oil blend works.

Health Canada's common-food data gives approximately:

- sunflower oil, 15 mL: 5.7 mg vitamin E
- canola oil, 15 mL: 2.4 mg
- olive oil contributes some more
- peanut butter, eggs, pepper and tomato products add the rest

So the weird sunflower-oil choice actually earns its place without requiring a mound of nuts/seeds.

## Zinc survived despite the plant foods

Plant zinc from pasta / soy / lentils has lower bioavailability because of phytate, but this meal also contains pork, eggs, milk and mozzarella.

Those animal-food sources supply a substantial fraction of the zinc target on their own, so the mixed-diet context is much better than a pure-legume calculation suggests.

## Choline: two eggs are doing heroic work

Two eggs provide roughly **~294 mg choline** using standard composition data.

Pork + milk + peas/soy + peanut butter carry the rest, putting the day around the 550 mg adult-male target without adding liver or supplements.

This is another reason the two eggs deserve to stay unless taste or convenience argues otherwise.

## Can we delete soy or lentils later?

Micronutrient answer: probably yes.

The audit suggests that removing both the 25 g soy and 20 g lentils would still leave calcium, potassium, magnesium, zinc, selenium, folate, B12 and choline in a strong range.

Their remaining jobs are:

- cheap protein
- fibre
- folate/iron insurance
- sauce texture
- price reduction

So they should stay only if they earn those jobs in the palatability/digestion tests. The meal does not need them as micronutrient life support.

## Carb slider implications

The micronutrient core is strong enough that the ~400 kcal carbohydrate slider can be chosen mostly for throughput and pleasure.

### Enriched white bread

Pros:

- extra folate / B vitamins / iron from enrichment
- cheap
- easy to eat
- works beautifully with margarine, jam, honey or sauce

### Maltodextrin

Pros:

- nearly pure calorie throughput
- almost zero chew

Micronutrient penalty:

- essentially none to lose, because the core already covers the target set well

This makes maltodextrin a legitimate *optional* performance tool if food volume becomes the actual problem, rather than something needed for nutrition.

## 002F conclusion

The Ultimate Meal now needs only two explicit plugs:

1. **~2 g iodized salt/day** for a reliable iodine design target
2. **~2 fatty-fish servings/week** for EPA/DHA

Everything else in the audited target set is already covered with breathing room by the 002E core.

That is a huge simplification. The next optimization can focus almost entirely on:

- taste
- digestion
- eating speed
- food mass
- cost
- how many ingredients can be removed before the meal gets worse

## Sources

- Health Canada Dietary Reference Intake tables: https://www.canada.ca/en/health-canada/services/food-nutrition/healthy-eating/dietary-reference-intakes/tables.html
- Health Canada Nutrient Value of Some Common Foods: https://www.canada.ca/en/health-canada/services/food-nutrition/healthy-eating/nutrient-data/nutrient-value-some-common-foods-2008.html
- Health Canada / CFIA iodized salt requirements: https://inspection.canada.ca/en/food-labels/labelling/industry/salt
- Health Canada iodide technical summary: https://www.canada.ca/en/services/health/publications/healthy-living/drinking-water-screening-value-iodide-technical-summary.html
- NIH ODS Choline: https://ods.od.nih.gov/factsheets/Choline-HealthProfessional/
- NIH ODS Zinc: https://ods.od.nih.gov/factsheets/Zinc-HealthProfessional/
- NIH ODS Selenium: https://ods.od.nih.gov/factsheets/Selenium-HealthProfessional/
- NIH ODS Omega-3 Fatty Acids: https://ods.od.nih.gov/factsheets/Omega3FattyAcids-HealthProfessional/
- USDA FoodData Central: https://fdc.nal.usda.gov/
