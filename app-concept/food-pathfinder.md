# Food Pathfinder — App Concept

Working product concept built from the food-experiment compendium.

The core product is not another recipe search box.

It is an interactive map that answers:

> **Given what I own, what I feel like, and how much hand-fuss I can tolerate, where can dinner go from here?**

---

## 1. Home screen: What do you have?

User inventory can be lightweight rather than obsessive.

### Permanent / likely stocked

- rice
- eggs
- yogurt / skyr
- soy sauce
- oils
- spices
- frozen vegetables

### Current perishables

- chicken thighs
- tofu
- salmon
- arugula
- leftover rice

### Flavour assets

- gochujang
- miso
- sofrito
- epis cubes
- curry paste
- sambal
- salsa verde

The user should be able to mark ingredients as:

- have
- usually have
- willing to buy
- do not want

---

## 2. Pick tonight's constraint

Instead of forcing the user to name a recipe, expose useful sliders / buttons:

### Effort

- almost zero hand work
- phone-compatible
- normal cooking is fine
- project / guest night

### Time

- under 15 min
- under 30 min
- under 60 min
- elapsed time irrelevant if mostly unattended

### Mood

- rich / comforting
- bright / fresh
- spicy
- brothy
- crispy
- creamy
- light-ish
- impressive

### Destination

Optional rather than required:

- surprise me
- East Asia
- Southeast Asia
- South Asia
- Middle East / North Africa
- Africa
- Europe
- Latin America / Caribbean

---

## 3. The main visualization: reachable food map

Center node:

> **Your kitchen right now**

Around it, show reachable intermediate states / dishes.

Example with:

- chicken thighs
- rice
- yogurt
- soy
- fish sauce
- gochujang
- frozen onion

Nearby destinations might be:

- gochujang chicken rice
- Vietnamese caramel chicken
- soy-braised chicken
- yogurt-marinated chicken

One purchase away:

- lemongrass paste -> Vietnamese lemongrass chicken
- curry paste + coconut milk -> Thai curry
- sumac -> sumac chicken
- chipotle -> chipotle-lime chicken

Two purchases away:

- prepared sofrito + olives -> arroz con pollo
- sambal + coconut milk -> nasi lemak / Malaysian lane

The map should make **culinary distance** visible.

---

## 4. Routes, not recipes

Tapping a destination shows several routes.

Example: **shawarma chicken rice**

### Route A — easiest

- bought shawarma seasoning
- chicken thighs
- oil
- air fryer
- rice cooker
- bought toum

### Route B — better marinade

- cumin / coriander / paprika / turmeric
- lemon
- garlic paste
- chicken
- Ziploc
- air fryer

### Route C — guest version

- full marinade
- chicken platter
- rice / pita
- toum + tahini
- pickles
- fresh herbs

Same destination, different effort path.

---

## 5. Ingredient unlock screen

Every high-leverage ingredient gets an “unlock tree.”

Example: **lemongrass paste**

Immediately unlocks:

- Vietnamese lemongrass chicken
- chicken inasal support
- Thai curry support
- Sri Lankan curry support
- coconut noodle soup support

Show:

- meals unlocked
- ingredients already owned that pair with it
- shelf life
- how much hand work it replaces

This could make grocery shopping feel like buying new abilities in a game.

---

## 6. Process unlock screen

Techniques can also be unlocked.

Example: **braise**

Once the user is comfortable with:

> brown -> add liquid / sauce -> cover -> leave alone

many destinations become easy:

- adobo
- ayam kecap
- cacciatore
- paprikash
- yassa
- Moroccan chicken
- dakbokkeumtang

This is useful because cuisines that look intimidating often share the same familiar process.

---

## 7. Intermediate-state inventory

The app should track prepared food assets, not only raw ingredients.

Examples:

- 2 portions cooked salsa chicken
- 3 epis cubes
- 1 bag frozen shawarma-marinated thighs
- leftover jasmine rice
- half jar pesto
- master soy sauce in freezer

Then it can answer:

> what can I make with almost no new cooking?

This is much closer to how a real kitchen works than standard recipe apps.

---

## 8. Leftover mutation mode

Input:

- leftover chicken
- leftover rice

Output a transformation tree:

- kimchi fried rice
- quesadilla
- burrito bowl
- lemon rice + chicken
- curry rice
- chicken congee / arroz caldo shortcut
- ochazuke-ish bowl
- pesto chicken rice experiment

The value proposition is:

> leftovers are nodes with outgoing edges, not dead inventory.

---

## 9. A 'vacation' button

One tap:

> **Take me somewhere else tonight.**

Algorithm prioritizes:

- cuisine/flavour profile not eaten recently
- ingredients already owned
- low additional purchases
- requested effort level

Example:

If the past three meals were East Asian, the app might surface:

- Trinidad pelau
- Cuban mojo chicken
- Greek lemon chicken
- Brazilian stroganoff

while still reusing chicken + rice.

---

## 10. Personal friction learning

After cooking, ask only a few questions:

- Delicious?
- Would you make it again?
- Annoying?
- Good leftovers?

Optional detail:

- which step sucked?

Examples:

- chopping onions
- raw-meat handling
- too many bowls
- sauce reduction needed babysitting
- too much chewing

The graph then personalizes path costs.

---

## 11. Taste vectors

Dishes can have soft descriptive coordinates:

- salty
- sweet
- sour
- spicy
- creamy
- fermented
- smoky
- herbal
- garlicky
- tomato-heavy
- coconut-heavy
- sesame/nutty
- brothy
- crispy

This enables recommendations like:

> something as bright and acidic as chipotle-lime chicken, but from a completely different cuisine

Possible answers:

- Greek lemon chicken
- yassa
- mojo chicken
- sumac chicken
- chicken inasal

---

## 12. Meal-family view

Instead of geography, visualize reusable architectures:

- Ziploc chicken -> air fryer
- one-pot chicken + rice
- chicken braise
- coconut curry
- fish in sauce
- egg + rice
- lentils cooked into sauce
- flavored rice + simple protein
- baked comfort slab

Each family fans out into cuisines.

This teaches the user that learning one method unlocks many places.

See [`../compendium/meal-families.md`](../compendium/meal-families.md).

---

## 13. Shopping optimizer

Question:

> I am going to the store. What five purchases unlock the most meals given what I already own?

Possible answer:

1. lemongrass paste
2. coconut milk
3. prepared sofrito
4. sumac
5. sambal

Each purchase displays a set of newly reachable dishes.

This is essentially a **set-cover / maximum-unlock** problem with shelf-life and price penalties.

---

## 14. Path cost

A path should not be scored only in minutes.

Potential cost function:

- hand minutes
- attention interruptions
- chopping
- dishes to wash
- raw-meat mess
- new purchases
- perishability / waste risk
- money

Potential rewards:

- expected enjoyment
- novelty
- calories / protein if desired
- leftover yield
- guest payoff
- ingredient usage before expiry

That lets the app optimize for things like:

> maximize novelty + deliciousness while keeping hand-fuss below 8 minutes

---

## 15. Recipe sources remain attached

Every destination should retain links to:

- original / culturally informative source recipe
- project adaptation
- personally tested version once one exists

So the app never becomes a context-free AI recipe blender.

The original recipe teaches what the dish is; the graph helps find the most compatible route into it.

See [`../compendium/source-library.md`](../compendium/source-library.md).

---

## 16. MVP

A first useful version does not need computer vision, grocery integrations or perfect nutrition data.

MVP could be:

1. manually curated ingredient / operation / dish dataset from this repo
2. simple inventory checklist
3. filters for hand-fuss / elapsed time / protein / cuisine
4. graph view of dishes reachable with 0, 1 or 2 purchases
5. route page with project notes + source link
6. thumbs-up / annoying feedback

The current repository already contains enough curated material to seed this.

---

# Longer-term weird / fun features

- **Cuisine adjacency map** — see how changing one ingredient moves a dish across flavour space.
- **What if? mode** — swap chicken for tofu / fish and see valid routes.
- **Fridge rescue** — prioritize ingredients nearing expiry.
- **Guest mode** — maximize wow-to-effort.
- **Bulk mode** — favor easy calories + adequate protein + low eating friction.
- **Pantry RPG** — jars/spices behave like unlockable abilities.
- **Skill tree** — learn braising, tempering, tahdig, wok cooking, etc. and unlock dish clusters.
- **Week itinerary** — seven destinations, deliberately low flavour repetition, high ingredient reuse.

---

# Product thesis

Most recipe apps ask:

> what do you want to cook?

Food Pathfinder asks:

> **where can your current kitchen go?**

The magic is making the transitions visible.

A chicken thigh should not appear as one ingredient associated with 500 unrelated recipe cards.

It should appear as a hub with paths radiating into Vietnam, Jamaica, Cuba, Korea, the Levant, India, Indonesia, the Philippines, Greece, Brazil and beyond.

That is the app version of the food atlas.