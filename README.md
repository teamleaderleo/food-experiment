# Food Experiment

A working notebook for building food that is delicious, nutritious, low-friction, easy to repeat, and flexible enough to feel different from night to night.

The project started as a cheap-meal experiment and turned into a broader question:

> **How do you build a small personal food universe where boring groceries can become wildly different meals without making cooking a second job?**

## Start here

Open [`playbook/food-passport.md`](playbook/food-passport.md).

That is the current quick-start guide: core groceries, flavour shelf, protein defaults, cuisine branches, strong first recipes, batch/reheat rules, and guest-night options.

For deeper browsing, open [`compendium/README.md`](compendium/README.md). The compendium lets you browse the same recipe universe by **cuisine, workflow, comparison matrix, or reusable flavour asset**.

The project now also has a runnable **Food Pathfinder v0** in [`prototype/index.html`](prototype/index.html): a 36-dish / 58-node graph prototype with geography ↔ morphology switching, inventory reachability, one-purchase unlock ranking, ingredient lenses, and personal friction weights. The model and success criteria are in [`app-concept/prototype-v0-spec.md`](app-concept/prototype-v0-spec.md).

## Current baseline

The real thing to beat is extremely simple:

- rice cooker white rice
- air-fryer chicken wings / chicken
- arugula
- olive oil
- freshly grated garlic
- Icelandic skyr with seeds mixed directly into the tub

See [`defaults/current-default.md`](defaults/current-default.md).

This baseline is strong because it requires very little hand work, very little cleanup, and almost no culinary attention.

## What to optimize for

Every experiment should be judged on:

1. **Taste** — would I actively want this again?
2. **Low-friction attention** — can the food mostly cook while attention goes elsewhere?
3. **Hands-on fuss** — chopping, sticky bowls, raw-meat handling, delicate timing, and cleanup all count.
4. **Easy calorie + protein delivery** — especially useful for the current bulk.
5. **Nutrition** — fibre, micronutrients, fish rotation, plant diversity, and sensible protein intake.
6. **Batch / reheat quality** — does tonight's cooking create an easy tomorrow?
7. **Ingredient overlap** — can the same groceries travel across cuisines?
8. **Cost** — keep it reasonable, then spend more when taste or convenience clearly improves.
9. **Guest-worthiness when desired** — a few dishes should look far more ambitious than the work required.

## Current project direction

The default protein pattern is now:

> **chicken + fish + tofu + eggs + dairy first; pork/beef as flavour-heavy rotation ingredients.**

Cooking style is **phone-compatible** rather than strictly “fast”:

- rice cooker
- air fryer
- oven / sheet pan
- braises and simmering
- one-pot meals
- Ziploc marinades
- slow cooker / pressure cooker
- casual leftovers

A 45-minute meal can be excellent if only 8 minutes require hands.

## Food-world highlights

The current notebook includes strong branches for:

- Taiwanese / Chinese comfort food
- Japanese donburi and curry
- Korean braises and rice bowls
- Vietnamese lemongrass chicken
- Thai curry and laksa
- Indonesian ayam kecap
- Filipino adobo
- Mexican / broader Latin flavours with premade pico/salsa
- Puerto Rican arroz con pollo / pollo guisado
- Jamaican jerk
- shawarma and Middle-Eastern sauces
- Indian butter chicken / curries
- Greek lemon chicken and seafood
- Portuguese peri-peri chicken
- Moroccan chicken / tagine
- Persian fesenjan
- pasta, ragù, baked pasta, and macarona béchamel
- whole-side salmon and other guest-worthy low-fuss food

## Repo map

- `playbook/` — current quick-start operating guides
- `compendium/` — cross-linked reference library by cuisine, workflow, matrix, and flavour asset
- `app-concept/` — graph model, math, cartography, version-control/social concepts, and prototype specifications
- `prototype/` — runnable Food Pathfinder experiments
- `defaults/` — meals and routines already in regular rotation
- `experiments/` — active recipe and workflow R&D
- `ingredients/` — groceries worth keeping around and what they combine with
- `shopping/` — shopping lists tied to experiments
- `pricing/` — dated cost research
- `research/` — broader findings and comparisons
- `templates/` — reusable experiment logs
- `recipes/` — meals that have earned promotion through repeated real-life use

## Promotion rule

An experiment becomes a recipe when it has been made several times and still feels worth buying ingredients for.

The final version should record the **easiest method actually used**, rather than the fanciest possible version.

The standard is simple:

> **Would future-me be happy to see this food in the fridge?**
