# Culinary Morphology + Geographic Atlas

**Status:** product concept notes

Food Pathfinder should contain more than a lineage graph.

There are at least three different relationships between foods:

1. **historical / cultural lineage** — influence, inheritance, migration, adaptation
2. **morphological similarity** — dishes that are structurally similar even when no historical relationship is claimed
3. **ingredient / technique diffusion** — where one ingredient, process, vessel, or flavour system appears across geography

Keeping these layers separate lets the app compare foods boldly without inventing history.

---

# 1. Morphology: Platonic meal families

A useful top-down view starts from abstract meal forms.

Examples:

## One-pot meat + rice

Abstract form:

> protein + aromatic base + rice + liquid + local flavour system -> covered cook

Nearby dishes include:

- Hainanese chicken rice
- Puerto Rican arroz con pollo
- Brazilian galinhada
- Somali bariis iskukaris
- Trinidad pelau
- Arabian kabsa
- Yemeni mandi
- Lebanese spiced chicken rice
- jollof + chicken variants

These dishes are culturally distinct. Their proximity on the morphology graph means only that the cooking architecture is similar.

## Protein + marinade + dry heat + starch

Nearby branches:

- Vietnamese lemongrass chicken
- Filipino chicken inasal
- Jamaican jerk chicken
- Cuban mojo chicken
- shawarma
- sumac chicken
- gochujang chicken
- miso salmon

## Aromatic paste + coconut milk + protein -> simmer

Nearby branches:

- Thai curry
- Malaysian kari ayam
- Sri Lankan chicken curry
- opor ayam
- ginataang manok
- Kerala fish curry
- laksa / coconut noodle branches

## Soft protein + broth + egg + rice

Nearby branches:

- sundubu jjigae
- oyakodon
- tofu + egg don
- arroz caldo / congee family at a broader level

The user can zoom out until dishes become archetypes, then zoom back down into specific regional implementations.

---

# 2. Similarity is not ancestry

The UI must clearly distinguish:

> **"these foods occupy nearby morphology-space"**

from:

> **"one historically influenced the other"**

The first can be inferred from ingredients / techniques / dish format.

The second requires historical evidence and should be represented separately, with provenance and sources.

This prevents a dangerous but tempting mistake:

> similar = descended from

Sometimes similarity comes from shared history. Sometimes from trade. Sometimes from similar ingredients / climate / constraints. Sometimes from independent invention.

The atlas should make that ambiguity visible rather than flatten it.

---

# 3. Top-down navigation

The user starts from an abstract family:

> **chicken + rice**

Then progressively adds constraints / identity:

`chicken + rice`

→ one pot

→ tomato-based

→ olives + sofrito

→ Puerto Rican arroz con pollo

Or:

`chicken + rice`

→ aromatic warm spices

→ cardamom / cinnamon / dried lime

→ Arabian kabsa

Or:

`chicken + rice`

→ coconut milk + pigeon peas + green seasoning

→ Trinidad pelau

This makes cuisine exploration feel like traversing a decision tree through food-space.

---

# 4. Bottom-up navigation

The user starts from one ingredient / technique and watches it radiate outward.

Examples:

## Tamarind

Possible branches:

- Thai massaman
- South Indian / Sri Lankan sour curries
- Kerala fish curry
- tamarind chutneys / sauces
- sweet-sour braises across Southeast Asia

## Coconut milk

Branches geographically across:

- Thailand
- Malaysia
- Indonesia
- Sri Lanka
- Kerala
- Philippines
- Burma / Myanmar
- Brazil
- Caribbean
- parts of East / West African cooking

The user can inspect how the same ingredient behaves differently in each context.

## Mustard seed

Possible branches:

- South Indian tempering
- Sri Lankan cooking
- pickles
- other regional spice systems

## Yogurt

Branches:

- Turkish çılbır
- South Indian curd rice
- marinades
- Middle-Eastern sauces
- Persian / South Asian rice and meat dishes

Bottom-up browsing turns an ingredient into a geographic passport.

---

# 5. Geographic rendering

The map should allow real geographic views.

Possible layers:

### Dish layer

Pins / regions for specific dishes.

### Ingredient layer

Where an ingredient is prominent or characteristic in documented dishes.

### Technique layer

Examples:

- clay-pot rice
- tandoor / high-heat roasting
- braising
- coconut-milk simmering
- fermentation
- griddled breads

### User-history layer

Places / regions whose food families the user has cooked.

The app can shade explored areas like a game map.

---

# 6. Geographic zoom should preserve locality

The atlas should work at multiple scales:

- world
- country
- region / province / state
- city
- town / island / community when reliable data exists

A cuisine should not always collapse to a nation-state label.

Examples of useful distinctions:

- Sichuan vs Cantonese vs Taiwanese food
- Kerala vs broader "Indian"
- Trinidad vs Jamaica vs Puerto Rico vs Haiti
- Basque vs generic Spanish
- northern Thai khao soi vs central Thai curry families
- regional / household adobo branches

When a small locality has a distinctive dish, the map should be able to show that as a local node rather than forcing it into a broad country bucket.

---

# 7. Ingredient -> geography -> dish exploration

A killer interaction:

Tap **coconut milk**.

The world map lights up.

Then explore:

- Thailand -> red curry / massaman
- Malaysia -> kari ayam / laksa / nasi lemak
- Indonesia -> opor ayam
- Sri Lanka -> chicken curry / dal
- Philippines -> ginataang manok
- Brazil -> moqueca
- Caribbean -> pelau / curry branches

Then tap **chicken thigh** as a second filter.

The graph contracts to dishes reachable with both.

Then tap **one pot**.

Now the map becomes a personalized culinary search space rather than an encyclopedia.

---

# 8. Morphological distance

Two foods can have a calculable structural distance.

Possible dimensions:

- protein class
- starch class
- cooking vessel
- heat method
- liquid / sauce family
- aromatic base
- spice family
- acid
- fat
- texture
- serving format
- number / type of operations

Example:

Pelau may be structurally close to arroz con pollo because both are one-pot chicken-rice meals, while still being flavour-distant because coconut milk / pigeon peas / caramel / green seasoning change several dimensions.

A morphology engine can answer:

> **"Show me something like this, but culturally and flavour-wise far away."**

That is a fantastic discovery query.

---

# 9. Convergent culinary evolution

An especially fun educational mode could show dishes that look like cousins despite weak / uncertain historical linkage.

The app can label these carefully as:

> **structural analogues**

rather than "related dishes."

Questions it can surface:

- Why do so many cultures independently arrive at meat + rice + aromatic broth?
- Why are yogurt + starch comfort foods common in multiple regions?
- Why do preserved / fermented condiments recur around staple grains?
- Why does coconut milk repeatedly become a rich cooking liquid in tropical regions?

This turns the app into a way to think about food systems, ecology, agriculture and household cooking constraints.

---

# 10. Historical links as optional evidence edges

When reliable evidence exists, a separate edge can represent:

- migration
- colonial influence
- trade route
- diaspora adaptation
- restaurant / commercial diffusion
- documented borrowing

These edges should cite sources and carry confidence.

Morphological similarity should never silently generate a historical edge.

This is important both intellectually and culturally.

---

# 11. Personal cartography

A user's personal map can be rendered in multiple coordinate systems.

### Geographic

Where in the world have your meals taken you?

### Morphological

Which meal families do you actually cook?

- braises
- one-pot rice
- curry + rice
- marinated dry-heat proteins
- egg meals
- tofu stews
- fish soups

### Ingredient

Which high-degree ingredients dominate your graph?

### Technique

Which cooking operations have become familiar?

This creates a much richer answer to:

> **"What kind of cook am I becoming?"**

---

# 12. Social maps

Comparing users becomes much more interesting when geography and morphology are both visible.

Example:

> You and Sam both cook lots of one-pot chicken + rice.
>
> Your graph clusters in Caribbean / Latin America.
> Sam's clusters in Arabian / East-African rice dishes.
>
> Closest untried swap:
> **you try kabsa; Sam tries pelau.**

Or:

> You both own coconut milk constantly.
> You use it mostly in Thai / Malaysian curries.
> Sam uses it in Brazilian / Caribbean dishes.
> Exchange one path.

---

# 13. The app becomes an atlas of transformations

At full zoom-out, the user sees broad archetypes.

At medium zoom, regional clusters appear.

At close zoom, individual dish families and household / author implementations appear.

At path level, exact ingredients, ratios, methods and substitutions appear.

So the same system supports:

> **Platonic meal form -> global family -> regional dish -> specific recipe -> someone's fork -> tonight's cook**

and the reverse:

> **this jar in my fridge -> dishes -> regions -> meal families -> global patterns**

That bidirectional navigation is a central product idea.

---

# Current thesis

Food Pathfinder should not force food into one tree.

It should let users move through several overlapping maps:

- **provenance map** — where documented lineages / influences lead
- **morphology map** — which foods resemble each other in ingredients / technique / format
- **geographic map** — where foods / ingredients / techniques appear
- **personal map** — which paths the user has actually traveled
- **social map** — how people's paths overlap / differ / fork

The magic comes from switching coordinate systems while looking at the same food.
