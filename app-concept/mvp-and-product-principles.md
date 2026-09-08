# Food Pathfinder — MVP + Product Principles

**Status:** product concept notes

The interesting product is not a prettier recipe database.

It is a **culinary pathfinding system** that treats cooking as a network of ingredients, flavour assets, intermediate states and transformations.

Core question:

> **Given what I have, how much fuss I can tolerate, and where I want dinner to go, what are the best paths from here?**

---

## Why this is fun

Most recipe apps make the user start with a finished dish name.

Food Pathfinder starts from the user's actual kitchen and lets them explore possibility space.

The emotional loop should feel closer to a game map than a cookbook:

- discover a new cuisine branch
- unlock it with one jar / spice / technique
- see neighboring dishes become reachable
- learn that two unfamiliar foods share the same underlying cooking method
- build reusable assets that shorten future routes

The app should make a person think:

> **"Holy shit, I can make all of that from what I already buy."**

---

# Product principles

## 1. Paths, not recipes

A recipe is one path through the graph.

The app should show alternatives:

- swap protein
- swap starch
- swap flavour identity
- change cooking method
- use a prepared shortcut
- use a leftover / freezer asset

The destination can change while most of the path stays the same.

---

## 2. Show culinary distance

Every candidate meal can have a rough distance from the current kitchen.

Possible dimensions:

- new ingredients required
- expected cost
- perishability of new purchases
- hands-on minutes
- attention density
- cleanup
- new technique burden
- cook time
- leftover payoff

Useful labels:

- **Here now** — no shopping
- **One unlock away** — one meaningful ingredient purchase
- **Easy detour** — a couple of purchases / minor technique
- **Weekend expedition** — special ingredients or more involved method

---

## 3. Let the user navigate by mood

The user should not need to know a dish name.

Possible intents:

- take me somewhere new
- almost no hand work
- phone-compatible
- use this chicken
- use leftover rice
- fish tonight
- vegetarian tonight
- something creamy
- something acidic / bright
- something spicy
- something impressive
- something I can eat tomorrow too
- something soft / low-chew

The graph filters itself around the request.

---

## 4. Make one purchase feel powerful

A key screen should answer:

> **What should I buy that unlocks the most interesting food?**

Examples:

- gochujang
- miso
- lemongrass paste
- Caribbean green seasoning
- prepared sofrito
- sambal
- Sri Lankan curry powder
- berbere
- sumac
- aji amarillo paste

Each ingredient card should show:

- meals unlocked
- cuisines unlocked
- shelf life
- ingredients already owned that pair with it
- first recommended dish

---

## 5. Reusable assets are first-class objects

The app should understand that these are inventory too:

- leftover rice
- marinated chicken bags
- master soy braising liquid
- frozen epis cubes
- tomato-masala cubes
- cooked salsa chicken
- ragù
- boiled eggs
- cooked curry base

A user's future options change substantially when these exist.

This is more powerful than merely tracking raw groceries.

---

## 6. Avoid obsessive inventory management

The user should not have to barcode every mustard bottle.

Inventory can have confidence levels:

- **always have**
- **probably have**
- **have now**
- **leftover / prepared now**
- **don't have**

The app can ask only when a missing ingredient actually affects the route.

---

# MVP

A useful first version can be surprisingly small.

## Data needed

### Ingredient nodes

Examples:

- chicken thigh
- rice
- egg
- yogurt
- coconut milk
- lime

Attributes:

- category
- pantry / fridge / freezer
- approximate shelf life
- common substitutions
- nutrition metadata later

### Flavour-asset nodes

Examples:

- gochujang
- curry paste
- sofrito
- epis
- miso
- sambal

### Operation nodes

Examples:

- marinate
- air fry
- roast
- braise
- pressure cook
- rice cook
- simmer
- fry egg
- blend

Attributes:

- active minutes
- unattended minutes
- attention density
- cleanup burden
- equipment

### Intermediate nodes

Examples:

- marinated lemongrass chicken
- cooked rice
- jollof base
- shredded salsa chicken
- boiled eggs

### Dish nodes

Examples:

- Vietnamese lemongrass chicken rice
- pelau
- sundubu jjigae
- nasi lemak
- chicken adobo

---

# First useful screens

## A. "My kitchen"

User selects / confirms:

- proteins
- starches
- vegetables
- flavour assets
- prepared leftovers

No gram-level tracking required.

## B. "Where can I go?"

Show reachable meals as a map or ranked cards.

Each card says something like:

> **Vietnamese caramel chicken**  
> You already have 5/5 core ingredients  
> 7 min prep · 15 min cook · one pan  
> New cuisine branch: Vietnam

or:

> **Nasi lemak**  
> Buy: coconut milk + sambal  
> Uses: rice, eggs, chicken already in kitchen  
> Unlocks 4 neighboring Malaysian meals

## C. Path view

Visual chain:

`chicken thigh`
+
`fish sauce + ginger + sugar`
→ **braise 12 min**
→ `caramel chicken`
+
`rice`
→ **dinner**

Then show side branches:

- add coconut milk → coconut caramel chicken
- swap ginger profile for lemongrass marinade → lemongrass chicken
- swap braise for air fryer → different texture / workflow

## D. "One purchase"

Rank ingredients by unlock value.

Example:

> **Buy lemongrass paste**
>
> Unlocks:
> - Vietnamese lemongrass chicken
> - chicken inasal
> - Thai curry variations
> - Sri Lankan curry
> - coconut noodle soups

## E. "Take me somewhere"

Randomized but constrained discovery.

Inputs:

- max purchases
- max hand-fuss
- protein preference
- cuisine recency / novelty

Output:

> Tonight: Trinidad pelau
>
> Why: one-pot, chicken-first, strong leftovers, uses rice + coconut milk + canned peas, cuisine not eaten recently.

---

# Ranking function

Early ranking can be heuristic rather than ML.

Possible score components:

**positive**

- ingredients already owned
- flavour novelty
- strong leftovers
- phone compatibility
- high user rating from previous cooks
- ingredient overlap with other unlocked dishes

**negative**

- new purchases
- perishability
- chopping
- dishes / cleanup
- constant attention
- unfamiliar difficult technique

The weights should be personalizable over time.

A user who enjoys chopping should not receive the same graph costs as a user who hates it.

---

# The killer interaction: live substitution

Imagine opening a dish and changing one node.

Example:

**Protein:** chicken thigh

Tap →

- tofu
- shrimp
- salmon
- ground chicken

The graph immediately updates:

- technique
- cook time
- sauce amount
- nutrition
- neighboring cuisines

Or tap:

**Method: skillet**

and replace with:

- air fryer
- oven
- pressure cooker

The app should tell the truth about quality loss rather than pretending every substitution is equivalent.

Examples:

- `air fryer`: 90% of intended result, much lower fuss
- `skip fresh herbs`: small loss
- `replace browned onions with frozen diced onion`: significant flavor loss in mujadara

This honesty is crucial.

---

# Graph motifs the UI can expose

The app can teach cooking indirectly by revealing recurring patterns:

### Bag marinade → dry heat → starch

Vietnamese lemongrass / jerk / mojo / shawarma / inasal / sumac chicken.

### Aromatic base → chicken → rice → covered cook

Arroz con pollo / pelau / bariis / galinhada / kabsa.

### Paste + coconut milk → protein → simmer

Thai curry / massaman / Sri Lankan curry / opor ayam / ginataang manok.

### Strong broth → soft tofu + egg

Sundubu / tofu-egg don / soup families.

### Flavoured rice → simple protein

Jollof / nasi lemak / lemon rice / tomato rice.

Once a user recognizes a motif, unfamiliar cuisines become less intimidating.

---

# Social / discovery layer later

Potential future features:

- people publish graph branches rather than only recipes
- compare regional variations
- "show me how households in X region branch from this base"
- provenance / source links for culturally specific recipes
- users rate substitutions separately from original versions
- community discovers the easiest high-quality path through a dish

A useful community contribution might be:

> "This recipe normally has nine hand steps. Here is the shortcut path that preserves 90% of what makes it good."

---

# Why this could be a real product

Most cooking software treats recipes as isolated documents.

Food is much more naturally represented as a **network of transformations and reusable state**.

The app becomes useful before, during and after cooking:

- **before:** choose a destination from current inventory
- **during:** follow the path / swap nodes
- **after:** leftovers and prepared assets automatically unlock tomorrow's options

The meal does not end when dinner is served. It changes the graph.

That is the central product idea.
