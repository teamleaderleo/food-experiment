# Coworker case study: SF delivery meal rotation

**Research snapshot:** 2026-10-24  
**Status:** candidate orders for a low-effort weekday routine; revisit menu prices, nutrition, and delivery eligibility at checkout.  
**Privacy:** Anonymous office-meal example. No employee name, workplace, health details, or delivery address.

## The decision

Find **delivered San Francisco lunches/dinners** that preserve a high-protein chicken-bowl routine while introducing more texture, different vegetables, legumes, and occasionally fish. Keep the ordering process simple enough to save a few repeat orders. The person likes paprika chicken and may be happy with the current food; these are optional experiments, not a prescribed diet.

Project criteria, adapted from [Food Experiment's existing priorities](../README.md#what-to-optimize-for):

- **Convenience:** delivery to the office, repeatable order, few choices.
- **Macro proximity:** compare against the *modeled* Kitava bowl, with an initial flexible range of about **850–1,150 kcal and 45–80 g protein** per meal. These are comparison bands, **not** recommended individual calorie/protein targets.
- **Texture/flavor:** retain appealing chicken, add crisp/pickled/bright/spicy elements so the entire meal does not eat like rice + softened potatoes + softened broccoli.
- **Nutrition:** rotate plant families, beans, leafy vegetables, and fish when desired. Avoid inferring micronutrient deficiencies from a single meal.
- **Cost:** compare **final delivered checkout totals**, net of usable rewards; do not mistake a menu subtotal for delivered cost.

## Kitava reference bowl: published components, not a weighed BYO order

Reference order: **double paprika chicken + jasmine rice + sweet potatoes + charred broccoli + ginger ponzu**.

Source: [Kitava's July 2026 full nutrition PDF](https://drive.google.com/file/d/16KjwsA3KS0a9AawL2YfvlBaRO-dCWCCi/view) (linked from the [Mission District menu](https://www.kitava.com/kitava-mission-district-menus/)). Values below are **arithmetic sums of full standalone listed component serving sizes**, with two servings for chicken. The build-your-own bowl's actual scoop sizes and amount of sauce consumed are **unverified**.

| Published component | Modeled amount | Calories | Protein | Carbs | Fat |
| --- | ---: | ---: | ---: | ---: | ---: |
| Paprika chicken | 2 × 113.4 g | 430 | 60 g | 4 g | 18 g |
| Jasmine rice | 172 g | 184 | 4 g | 40 g | 0.2 g |
| Sweet potatoes | 221.2 g | 251.4 | 3.4 g | 42.9 g | 7.8 g |
| Charred broccoli | 158.2 g | 67.6 | 4.4 g | 10.4 g | 2.2 g |
| Ginger ponzu | 57 g | 139 | 0 g | 35 g | 0 g |
| **Reference sum** | **All listed servings** | **1,072** | **71.8 g** | **132.3 g** | **28.2 g** |

**Fiber in the full-serving model:** about **12.3 g**. Kitava lists **139 kcal, 30.3 g sugar, and 2,155.6 mg sodium** for a full **57 g** ginger-ponzu serving; actual sauce eaten could be much less. For example, half the modeled broccoli serving reduces the bowl by roughly **34 kcal, 2.2 g protein, and 5.2 g carbs**. The PDF gives macronutrients and select label data; it does not give complete vitamin/mineral coverage.

### Near-macro-preserving Kitava variations

All retain **double paprika chicken and jasmine rice**. Change just one component, using the PDF's full-serving figures, and confirm the restaurant lets you make that selection.

| One change | Modeled kcal | Protein | Carbs | Fat | Why try it |
| --- | ---: | ---: | ---: | ---: | --- |
| Original reference | 1,072 | 71.8 g | 132.3 g | 28.2 g | Familiar control |
| Replace broccoli with **cumin beans** | **1,068** | **71.9 g** | **133.9 g** | **27.1 g** | Legume rotation, almost identical macros |
| Replace broccoli with **za'atar cauliflower** | **1,114** | **71.2 g** | **132.2 g** | **33.4 g** | Different seasoning and vegetable |
| Replace sweet potatoes with **fingerling potatoes** | **998** | **71.4 g** | **117.4 g** | **27.1 g** | Less sweetness, still a potato |
| Replace ponzu with **romesco** | **1,066** | **74.6 g** | **104.4 g** | **39.5 g** | Nutty/savory sauce, less sugar and more fat |

A distinct optional protein rotation: replace one **113.4 g paprika chicken serving** (215 kcal, 30 g protein, 2 g carbs, 9 g fat) with one **127.6 g salmon serving** (177 kcal, 30 g protein, 0 g carbs, 5 g fat). That produces a modeled **1,034 kcal / 71.8 g protein / 130.3 g carbs / 24.2 g fat** bowl. Mixed proteins may require a side order; availability and price must be checked. Because chicken is the preferred protein, this is a lower-priority option.

### Tiny additions, if changing the order sounds annoying

- **Fresh cracked black pepper:** near-zero macro effect at culinary quantities; add aroma and bite.
- **Lime, vinegar, or pickled red onion:** brighten the sweet/savory profile.
- **Cucumber, radish, cabbage, or scallions:** add crispness and a different texture; choose what the restaurant offers.
- **Toasted pepitas or sesame:** crunch and some fats/minerals; account for the extra calories if closely tracking.
- **A second sauce:** an easy way to rotate flavor, but creamy/oil-rich sauces may change fat/calories more than pepper or lime.

## Other delivery candidates — published menu figures

Figures are for the exact named orders indicated, **not** hypothetical added proteins. Restaurants may vary by SF location; verify the office address in the ordering flow.

| Restaurant / exact order | Calories | Protein | Carbs | Fat | Fiber | Texture/variety payoff | Macro comparison |
| --- | ---: | ---: | ---: | ---: | ---: | --- | --- |
| **[Ben's Fast Food](https://bensfastfood.com/menu): Chicken Hearty Bowl + 8 oz Slow Roasted Chicken side** | **950** | **72 g** | **65 g** | **40 g** | **10 g** | Cucumber, pickled onions, sunflower seeds, carrots; extra chicken | Similar protein; fewer carbs and ~122 fewer kcal |
| **[MIXT](https://www.mixt.com/menu/mixt/): Mediterranean Bowl (standard)** | **930** | **46 g** | **80 g** | — | **14 g** | Quinoa, cabbage, pickled red onion, walnuts, pita crisps; more varied crunch | About 26 g less protein; add chicken *only after recalculating* |
| **[Sweetgreen](https://www.sweetgreen.com/nutrition/): Hot Honey Chicken (standard)** | **845** | **49 g** | **66 g** | **38 g** | **7 g** | Cabbage slaw, crispy onions, quinoa, chicken, roasted sweet potatoes | Lower protein and carbs; sweet/savory profile remains familiar |

**Ben's math:** official [menu](https://bensfastfood.com/menu) lists Chicken Hearty Bowl **610 kcal / 27 g protein / 63 g carbs / 25 g fat / 9 g fiber** and 8 oz chicken side **340 kcal / 45 g protein / 2 g carbs / 15 g fat / 1 g fiber**. Totals are their sums. The side is an additional purchased item; confirm availability and price.

**MIXT:** the [official menu](https://www.mixt.com/menu/mixt/) publishes 930 kcal / 46 g protein / 80 g carbs / 14 g fiber for the Mediterranean Bowl. It does **not** publish its fat grams on that menu, so they are intentionally left blank here. The [nutrition calculator](https://www.mixt.com/nutrition-calculator/) is the place to recalculate customized chicken portions.

**Sweetgreen:** the [official nutrition guide](https://www.sweetgreen.com/nutrition/) lists Hot Honey Chicken at 845 kcal / 49 g protein / 66 g carbs / 38 g fat / 7 g fiber. Some Sweetgreen menu views show a different calorie value; use the specific nutrition-guide version and check the local order.

**Best first experiments:** (1) original Kitava with cumin beans or a more savory sauce, (2) Ben's Chicken Hearty Bowl **plus** chicken side, (3) MIXT Mediterranean Bowl for a higher-variety, lower-protein day. Sweetgreen is another convenient option. No need to force every single meal to contain 72 g protein.

## Kitava delivery vs DoorDash with DashPass

**Can Kitava deliver without visiting the store? Yes.** [Kitava's own website](https://www.kitava.com/) offers online **pickup or delivery** for SF. The ordering workflow may use a third-party ordering/courier partner; the distinction here is initiating an order **through Kitava's website while signed in**, versus through the DoorDash marketplace.

- [Kitava Mission online ordering](https://order.online/store/kitava-32001): listings observed on 2026-10-24 show a BYO Bowl starting at approximately **$10 for pickup** and **$11.99 in the delivery view**. These are **base prices, not the customized double-chicken delivered total**. Prices and fees vary by mode, time, destination, and options.
- [Kitava Rewards](https://www.kitava.com/rewards/): **5 points per $1** of eligible food/beverage purchases; **500 points = $5 credit**, roughly **5% back in redeemable store credit**. Sign in when ordering through Kitava's website. Third-party marketplace orders and catering are excluded; rewards expire **60 days after issuance**.
- [Mission menu](https://www.kitava.com/kitava-mission-district-menus/) states a **5% employee-healthcare surcharge**; check how it appears in the final total.
- **DashPass** can reduce some marketplace delivery/service charges, so its effective price could still win. Compare full **food + customizations + surcharge + tax + delivery + service fees + tip**, then subtract only rewards the person expects to use.
- Ordering two meals together may reduce repeat delivery costs; refrigerate the second promptly if it will be eaten later.
- A recurring-direct-order request is reasonable for someone purchasing frequently, but **no standing discount has been confirmed**. Catering minimums and catering menus are a separate product.

### Reusable checkout comparison

| Line item | Kitava.com delivery | DoorDash + DashPass |
| --- | ---: | ---: |
| Identical double-chicken bowl subtotal | TBD | TBD |
| Surcharges / tax | TBD | TBD |
| Delivery + service fees | TBD | TBD |
| Tip | TBD | TBD |
| **Checkout charged** | **TBD** | **TBD** |
| Usable rewards credit earned | TBD | $0 Kitava Rewards |
| **Effective cost** | **TBD** | **TBD** |

Do this once with the **same bowl and same office delivery address** and save the less costly ordering method. At **40 orders/month**, each **$1/order** difference is about **$40/month**; **$2/order** is about **$80/month**. Those are scenario calculations, not a verified discount.

## Low-friction test plan

1. **Keep the familiar Kitava order** as the control; no need to replace something the person likes.
2. **Try one Kitava ingredient or sauce swap**. Photograph or save the exact receipt/configuration, and note actual portions eaten.
3. **Try one Ben's extra-chicken order** and one MIXT or Sweetgreen order as delivered to the office. Compare actual cost, satisfaction, and whether it is easy to reorder.
4. **Try one Kitava.com vs DashPass checkout comparison** for the exact same bowl, including all fees and usable rewards.
5. Keep the **two or three winners** as saved repeat orders. Recheck nutrition labels/menu formulations when they change.

This is an informal menu-comparison project, not a personal nutrition diagnosis. The current baseline is a **full-component serving model**; a food scale or confirmed BYO portions would give a closer match to what actually arrives.
