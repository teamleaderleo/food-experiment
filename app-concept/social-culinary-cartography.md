# Social Culinary Cartography — Share the Graph, Not Just the Photo

**Status:** product concept notes

The social object in Food Pathfinder should not be a food photo with a caption.

It should be the **path through food-space**.

A cook should be able to say:

> **Here is where I started, here is the branch I took, here is what I changed, here is how it turned out, and here is what I want to try next.**

That is much richer than posting a finished plate.

---

# 1. A cooking history is a traversed graph

Every real cooking session creates a path:

`ingredients on hand`
→ `flavour asset / marinade`
→ `technique`
→ `intermediate state`
→ `finished dish`
→ `rating / notes`
→ `leftovers / new assets`

Over time, one person's food life becomes a personal subgraph of the global food graph.

The important thing is not merely which recipes were completed.

It is:

- which branches were explored
- which paths were repeated
- which substitutions worked
- which shortcuts were accepted
- which cuisines became familiar
- which techniques became easy
- which nodes were disliked
- which ingredients became permanent inventory

---

# 2. "Here's my graph"

A profile should be able to show a visual food map rather than a photo grid.

Possible views:

## Cuisine map

Clusters for:

- Vietnam
- Korea
- Japan
- Trinidad
- Sri Lanka
- Brazil
- Lebanon
- Persia
- etc.

Nodes brighten / grow as the user actually cooks dishes in that cluster.

A person might visibly have:

- deep Korean / Japanese branches
- a new Caribbean frontier
- one lonely Persian expedition
- almost no Spanish seafood yet

That is immediately more expressive than "12 recent food photos."

## Technique map

Show paths through:

- air fryer
- braise
- one-pot rice
- curry
- stir-fry
- pressure cooker
- bake
- soup
- fermentation / pickling later

Two people who eat totally different cuisines may discover that they cook through almost the same technique graph.

## Ingredient graph

Show high-degree personal nodes:

- chicken thighs
- rice
- eggs
- tofu
- coconut milk
- gochujang
- miso
- sofrito
- epis

This exposes a person's actual cooking vocabulary.

---

# 3. Path sharing

A shareable cooking post should look more like a mini route card.

Example:

**Vietnamese caramel chicken — Leo's path**

Started with:
- chicken thighs
- fish sauce
- ginger
- sugar
- rice

Path:

`thighs + fish sauce + ginger + sugar`
→ `12-minute braise`
→ `glossy caramel chicken`
+
`rice cooker rice`
→ `dinner`

Modifications:
- used ginger paste
- skipped shallot
- doubled sauce

Result:
- 9/10 taste
- very low fuss
- excellent next day
- would repeat

Next branches:
- coconut caramel chicken
- lemongrass chicken
- ayam kecap

That post teaches something reusable.

---

# 4. Implementations belong under recipe concepts

A recipe concept should not be one canonical text document.

Think:

**Dish concept:** chicken adobo

Then many implementation paths:

- bone-in traditional-ish stovetop
- boneless-thigh weeknight braise
- pressure-cooker version
- extra-sauce batch version
- soy-light version
- someone's failed over-reduced version

Each implementation can be rated separately.

This lets the app preserve culinary identity while still admitting that real cooks make different compromises.

---

# 5. Rate the path, not only the destination

A dish can taste great and still be a terrible path for a particular person.

Each cooked path can record:

- taste
- hand-fuss
- attention density
- cleanup
- ingredient annoyance
- repeat desire
- next-day quality
- guest payoff
- eating ease

Then the system learns things like:

> "You love this flavour but hate this implementation."

That is much more useful than a single five-star recipe rating.

---

# 6. Personal edge weights

The same edge has different cost for different people.

Examples:

`dice onion`
- cheap edge for someone who likes chopping
- expensive edge for someone who hates it

`braise 45 minutes`
- cheap if mostly unattended

`deep fry`
- expensive if oil cleanup is hated

`buy prepared pico`
- cheap if convenience spend is acceptable

Over time, a person's graph should acquire personal edge weights from actual behavior.

Then pathfinding becomes genuinely personal.

---

# 7. Social graph comparison

Comparing two people's food graphs could be extremely fun.

## Overlap

> You and Alex both cook:
> - Japanese curry
> - shawarma chicken
> - Thai red curry
> - oyakodon

## Divergence

> Alex has explored:
> - Persian rice
> - Ethiopian stews
> - Georgian chicken
>
> You have explored:
> - Caribbean chicken/rice
> - Vietnamese braises
> - Korean tofu stews

## Suggested exchange

> "You each have 4 dishes the other person hasn't tried. Swap one route this week."

This creates social discovery from actual cooking histories rather than popularity feeds.

---

# 8. Culinary fingerprints

A profile could generate a dynamic culinary fingerprint from graph statistics.

Not a personality quiz. Actual behavior.

Possible dimensions:

- cuisine breadth
- technique breadth
- ingredient reuse
- average hand-fuss
- novelty rate
- repeat rate
- vegetarian / seafood / poultry balance
- spice / acid / richness preferences
- batch-cooking frequency
- guest-food frequency

Example:

> **Your graph:**
> - high cuisine breadth
> - very high chicken-thigh reuse
> - strong rice-centered topology
> - low chopping tolerance
> - high marinade diversity
> - emerging fish branch
> - underexplored baked comfort food

The app can then suggest new frontiers adjacent to the user's current graph.

---

# 9. Streaks should be exploration streaks, not calorie streaks

Possible game mechanics:

- cook 3 new cuisine branches this month
- try 5 transformations from the same chicken-thigh node
- complete a coconut-curry cluster
- explore 3 fish-in-sauce paths
- cook one guest-mode centerpiece
- use one leftover asset in three different destinations

Achievements should reward curiosity and capability, not obsessive logging.

---

# 10. A path has provenance

For culturally specific food, every graph path should be able to preserve links to:

- original source recipes
- cultural / regional context
- known variations
- project adaptation notes

That helps distinguish:

- "this is chicken adobo"
- "this is inspired by adobo"
- "this is a shortcut branch that preserves some key traits"

The graph should support adaptation without pretending all paths are equivalent or equally traditional.

---

# 11. Community contributions become graph edits

The most valuable contribution may be:

> "I found a better path from A to B."

Examples:

- replacing fresh lemongrass with a specific paste preserved 90% of the result
- air-fryer version worked better than skillet for this marinade
- frozen onion destroyed the quality of this particular dish
- pressure-cooker route cut attention dramatically with little quality loss
- this store-bought sauce unlocked three good meals

Users can publish:

- alternate edges
- substitutions
- shortcut paths
- flavour-asset nodes
- leftover transformations

The community improves the map itself.

---

# 12. "Where have you been?"

A beautiful profile screen could show:

- cuisines visited
- favorite routes
- recent expeditions
- dishes repeated most
- high-rated implementations
- failed branches
- unexplored neighboring clusters

This makes cooking history feel like travel history.

A year of eating becomes visible as a map.

---

# 13. "Where should I go next?"

The social layer can drive recommendations from graph comparison.

Examples:

> "Three people whose graphs overlap strongly with yours all loved chicken inasal."

> "You have cooked five coconut curries but never opor ayam. It is one ingredient away."

> "Your friend cooks a version of pelau that uses the same green seasoning you already own."

> "You both cook a lot of chicken/rice. Their highest-rated unfamiliar branch is Somali bariis."

This is much better than generic trending recipes.

---

# 14. Shareable graph fragments

Full graphs may be visually overwhelming.

Users should be able to share a fragment:

### "My chicken-thigh universe"

Center:
- chicken thigh

Branches:
- lemongrass
- jerk
- mojo
- shawarma
- inasal
- gochujang
- miso
- curry
- adobo

Or:

### "What I did with leftover rice this month"

- lemon rice
- kimchi fried rice
- gyeranbap
- nasi-goreng-ish
- tomato rice

These fragments are simultaneously personal, instructional and fun.

---

# 15. Photos become evidence, not the product

A photo can still attach to a path.

But its role is:

- show how the implementation turned out
- document texture / browning / presentation
- help compare variants

The interesting social object remains the graph path.

> **Photo: what I made.**  
> **Path: how I got there.**  
> **Graph: what I've learned and where I can go next.**

---

# Current thesis

The social cooking product should feel less like Instagram for food and more like **Strava + a strategy-game tech tree + a world atlas for cooking**.

People should be able to say:

> **"Here's my fucking graph."**

and that graph should actually tell you something useful:

- what they cook
- how they cook
- what they like
- which shortcuts they trust
- what they've learned
- where they've traveled culinarily
- what you could steal from their path
