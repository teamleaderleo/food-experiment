# Food Transformation Graph

This is the conceptual model hiding underneath the whole project.

The food atlas is not really a list of recipes. It is a network of ingredients, flavour assets, intermediate states, cooking operations and finished meals that can be recombined.

A useful app should model that network directly.

---

## Core idea

A normal graph is slightly too simple because cooking steps often consume several things at once.

A better abstraction is a **directed hypergraph**:

> several ingredient/state nodes + one cooking operation -> a new state / component / dish

Example:

- chicken thighs
- lemongrass paste
- fish sauce
- sugar
- garlic

plus the operation:

- `marinate in bag`

produces:

- `Vietnamese-style marinated chicken`

Then:

- marinated chicken

plus:

- `air fry`

produces:

- `cooked lemongrass chicken`

Then:

- cooked lemongrass chicken
- rice
- bought pickles / greens

produces:

- `lemongrass chicken rice bowl`

The same chicken node can take a completely different outgoing path through jerk seasoning, shawarma spices, miso, mojo, sumac, chipotle or gochujang.

---

# Node types

## 1. Base ingredients

Examples:

- chicken thighs
- salmon
- cod
- tofu
- eggs
- rice
- pasta
- potatoes
- yogurt / skyr
- canned beans

These are the boring inventory nodes.

## 2. Identity ingredients

Examples:

- gochujang
- miso
- berbere
- kecap manis
- chipotle in adobo
- aji amarillo paste
- curry powder
- sambal
- sumac
- pomegranate molasses

See [`identity-ingredients.md`](identity-ingredients.md).

## 3. Aromatic bases

Examples:

- sofrito
- epis
- Caribbean green seasoning
- ginger-garlic paste
- lemongrass paste
- tomato-masala freezer cubes

See [`aromatic-bases.md`](aromatic-bases.md).

## 4. Cooking operations

Examples:

- marinate
- air fry
- braise
- simmer
- pressure cook
- rice cook
- bake
- roast
- fry
- temper spices
- blend
- reduce
- chill / rest

Operations should carry metadata:

- active minutes
- elapsed minutes
- attention density
- cleanup friction
- appliance
- batchability
- whether raw-meat handling is required

## 5. Intermediate states

This is the category recipe sites usually hide, but it is incredibly valuable.

Examples:

- marinated raw chicken bag
- cooked salsa chicken
- master soy braising liquid
- tomato masala
- jollof red base
- cooked rou zao
- cooked ragù
- boiled eggs
- leftover rice
- coconut-pandan rice
- prepared curry sauce

Intermediate states are often the key to low-friction future meals.

## 6. Finished components

Examples:

- air-fried jerk chicken
- lemon rice
- coconut rice
- misir wat
- Greek gigantes
- tahini sauce
- skyr crema

## 7. Finished dishes

Examples:

- oyakodon
- nasi lemak
- pelau
- arroz con pollo
- sundubu jjigae
- moqueca
- butter chicken + rice
- chicken shawarma bowl

---

# Edge / transformation metadata

Every transformation can be scored on the dimensions the project already cares about:

- hands-on minutes
- elapsed minutes
- attention density
- mess / cleanup
- phone compatibility
- knife work
- raw-meat handling
- appliance requirements
- leftovers
- freezer quality
- approximate cost
- approximate calorie density
- protein contribution
- fibre / vegetable contribution
- guest payoff
- confidence / tested status

This means pathfinding can optimize for real life instead of simply finding the shortest recipe.

---

# Cuisine is a label on paths, not a prison

Cuisine should be represented as contextual metadata rather than forcing every dish into one rigid box.

For example:

`chicken thighs -> Ziploc marinade -> air fryer -> rice`

is a reusable skeleton.

Identity injections create different paths:

- lemongrass + fish sauce -> Vietnamese lane
- jerk seasoning + lime -> Jamaican lane
- sumac + lemon -> Palestinian-inspired lane
- chipotle + lime -> Mexican-inspired lane
- miso + mirin -> Japanese lane
- mojo -> Cuban lane
- calamansi + lemongrass + annatto -> Filipino inasal lane

The app should make these sibling paths visually obvious.

---

# Substitution edges

Some nodes should be connected by explicit substitution relationships.

Examples:

- chicken thighs <-> chicken breast
- ground pork <-> ground chicken
- fresh onion <-> frozen diced onion
- fresh ginger <-> ginger paste
- fresh lemongrass <-> lemongrass paste
- homemade pico <-> purchased pico
- Chinese sesame paste <-> tahini (imperfect but useful)
- fresh fish fillet <-> frozen boneless fillet when method permits

Substitution edges need a **quality penalty / character change** rather than pretending swaps are identical.

Example:

> fresh lemongrass -> lemongrass paste: tiny authenticity / texture loss, huge labour reduction

That is exactly the trade the project often wants.

---

# Food distance

The graph makes it possible to define a useful concept:

> **How far away is another meal from what I already own / prepared?**

Distance can include:

- number of new groceries
- cost of new groceries
- number of new techniques
- extra active minutes
- extra cleanup
- perishability burden

Example:

If the kitchen already has chicken thighs, rice, soy sauce, fish sauce, ginger paste and sugar:

- Vietnamese caramel ginger chicken may be **distance 0–1**
- lemongrass chicken may be **distance 1** (buy lemongrass paste)
- Thai curry may be **distance 2** (curry paste + coconut milk)
- fesenjan may be **distance 4+** (walnuts, pomegranate molasses, saffron/spices, longer process)

This could be far more useful than generic recipe search.

---

# Pathfinding questions the app should answer

## Inventory-first

> I have chicken thighs, rice, eggs, skyr and gochujang. What can I make?

Return several paths sorted by friction / novelty / payoff.

## Destination-first

> I want something Malaysian.

Show the shortest paths from current inventory to nasi lemak, laksa, kari ayam, etc.

## Effort-first

> I have 10 hands-on minutes and 45 minutes elapsed time. I want my phone free for most of it.

Filter transformations by attention density.

## Ingredient-first

> I bought a jar of sambal. What did that unlock?

Show reachable dishes and nearby ingredients that expand the cluster.

## Leftover-first

> I have cooked rice and leftover chicken.

Show conversion paths:

- kimchi fried rice
- lemon rice + chicken
- nasi-goreng-ish rice
- burrito bowl
- ochazuke-ish branch
- curry rice

## Novelty-first

> Give me the meal furthest from what I ate this week while reusing the same groceries.

This is where the vacation idea becomes computational.

---

# The graph should learn from real life

Every time a dish is made, record:

- did I like it?
- would I make it again?
- actual hands-on annoyance
- actual cleanup
- first-night quality
- leftover quality
- ingredient waste
- substitutions used
- what step felt stupid

Then edge costs change for the user.

A theoretically 10-minute recipe that feels annoying becomes expensive in the personal graph.

A 60-minute braise that required six easy minutes becomes cheap.

---

# Important distinction: recipe graph vs personal graph

The global graph says what is possible.

The personal graph says what is worth doing.

That difference is the entire project.

---

# Existing compendium pieces map naturally into the graph

- [`recipes-by-cuisine.md`](recipes-by-cuisine.md) = cuisine-labelled dish clusters
- [`recipes-by-workflow.md`](recipes-by-workflow.md) = operation clusters
- [`meal-families.md`](meal-families.md) = recurring graph motifs
- [`identity-ingredients.md`](identity-ingredients.md) = high-degree ingredient nodes
- [`aromatic-bases.md`](aromatic-bases.md) = reusable intermediate/input nodes
- [`flavor-assets.md`](flavor-assets.md) = persistent intermediate nodes
- [`rice-passport.md`](rice-passport.md) = starch-first subgraph
- [`recipe-matrix.md`](recipe-matrix.md) = flattened table view of graph metadata

The compendium is already a human-readable prototype of the eventual data model.

---

# Current thesis

The app is not fundamentally a recipe app.

It is a **pathfinding system through food space**.

> start with what exists -> add one or two high-leverage things -> apply a low-friction transformation -> arrive somewhere delicious

The interesting product question is not “what recipe should I cook?”

It is:

> **what destinations are reachable from my kitchen tonight, and what is the cheapest / easiest / most exciting path to each one?**
