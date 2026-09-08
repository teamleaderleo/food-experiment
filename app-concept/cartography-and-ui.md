# Food Pathfinder — Cartography + UI Concepts

**Status:** product / interaction design notes

The graph becomes fun when the interface lets the user *feel* the topology instead of reading a database.

The core design challenge is:

> **How do we make a huge food graph explorable without turning it into an unreadable hairball?**

The answer is probably multiple coordinated maps, semantic zoom, local neighborhoods, and strong filtering rather than one giant static graph.

---

# 1. The home view should be local, not global

Do not open on 50,000 recipe nodes.

Open on:

> **Your kitchen right now**

Center node:

`current kitchen state`

Nearby reachable regions:

- here now
- one purchase away
- easy detours
- weekend expeditions

This makes the graph immediately actionable.

---

# 2. Semantic zoom

Zoom level changes what a node represents.

Possible hierarchy:

### World view

- large cuisine / morphology clusters

### Region view

- countries / regional cooking systems

### Local culinary view

- dish families

### Dish view

- implementations / variants

### Path view

- ingredients + operations + intermediate states

### Cook-log view

- user's specific fork / rating / substitutions

The user should be able to zoom from:

`Southeast Asia`

into:

`Vietnam`

into:

`lemongrass chicken`

into:

`air-fryer weekday fork`

into:

`my v3: more ginger, less sugar`

without mentally switching apps.

---

# 3. Coordinate-system switcher

Same food universe, different layout logic.

Possible map modes:

### Geography

Place dishes where they are associated geographically.

### Morphology

Arrange dishes by structural cooking similarity.

### Flavour

Arrange by aromatic / acid / spice / fat profile.

### Workflow

Arrange by cooking pattern:

- Ziploc + air fryer
- one-pot rice
- braise
- soup
- curry
- baked tray

### Personal history

Arrange by what the user has cooked and how often.

### Social

Arrange by overlap with friends / communities.

The magic interaction:

> **toggle coordinate systems and watch the world rearrange.**

A dish that is far away geographically may snap next to a familiar dish in morphology view.

---

# 4. Layers rather than one truth

Map overlays can be toggled independently:

- cultural / provenance links
- structural similarity
- shared ingredients
- shared techniques
- geography
- user history
- friend history
- popularity
- seasonality
- cost
- nutrition
- pantry reachability

This is important because a single line between two dishes is ambiguous.

Different edge styles can mean different things.

Never visually imply ancestry when the edge only means structural similarity.

---

# 5. Contour maps of culinary effort

Imagine the map shaded by culinary distance from the current kitchen.

Center:

- no-purchase meals

Then expanding contours:

- one ingredient away
- two ingredients away
- new technique required
- special-shopping expedition

Like hiking elevation, but the terrain cost is:

- shopping
- hand-fuss
- technique
- cleanup

A user could literally choose:

> **show me everything below effort elevation 3.**

---

# 6. Fog of war

The user's personal map does not need to reveal everything at once.

Possible states:

- cooked and rated
- discovered but not cooked
- neighboring unexplored
- distant / hidden

Trying a cuisine reveals nearby branches.

Example:

Cook Vietnamese lemongrass chicken.

The map reveals:

- caramel ginger chicken
- pho-adjacent soup lane
- bun / vermicelli serving format
- fish-sauce marinade family

This creates genuine game-map discovery without pretending food is a completion checklist.

---

# 7. Personal trails

Instead of only dots showing cooked dishes, draw the user's chronological trail.

Example:

`current wings`
→ `gochujang wings`
→ `dakbokkeumtang`
→ `sundubu`
→ `Korean fish braise`

You can see how one familiar ingredient or sauce pulled the user into a region.

Another trail might be:

`plain rice`
→ `nasi lemak rice`
→ `laksa`
→ `kari ayam`
→ `ayam kecap`

That is an actual culinary journey.

---

# 8. Fork trees

A dish page can have a tree view of implementation branches.

Example:

`lemongrass chicken`

├─ fresh lemongrass + grill
├─ paste + skillet
├─ paste + air fryer
│  ├─ rice serving
│  └─ vermicelli serving
└─ salmon fork

Each branch can display:

- who cooked it
- rating
- active effort
- key diff
- fidelity notes

The user can visually choose a route before opening detailed instructions.

---

# 9. Recipe diff UI

Diff should be visual and culinary, not code-like by default.

Possible format:

### Changed

- chicken thigh -> salmon
- grill -> air fryer
- plain rice -> coconut rice

### Added

- pico

### Removed

- fresh herb salad

### Expected effect

- less chopping
- more fish richness
- less char
- more coconut sweetness

This communicates modification better than a paragraph of comments.

---

# 10. Timeline / commit history

A personal dish page can show actual evolution:

### v1

Original source path — 7/10

### v2

Boneless thighs — 8/10

### v3

Lemongrass paste + air fryer — 9/10

### v4

Chicken breast — 6/10, reverted

### Stable

v3

This turns cooking experience into durable knowledge.

---

# 11. Ingredient lens

Tap an ingredient and the graph re-centers around it.

Example:

`coconut milk`

Branches radiate to:

- Thai red curry
- massaman
- laksa
- opor ayam
- Sri Lankan chicken curry
- ginataang manok
- moqueca
- nasi lemak rice

Then secondary rings show:

- proteins commonly paired
- regions
- cooking methods
- other identity ingredients

This is the bottom-up exploration mode.

---

# 12. Technique lens

Tap:

`braise`

See:

- adobo
- ayam kecap
- yassa
- paprikash
- cacciatore
- Moroccan chicken
- dakbokkeumtang
- jjimdak

Then filter by:

- chicken only
- under 15 active minutes
- strong leftovers
- new cuisine only

The app teaches that the user already knows more cooking than they think.

---

# 13. Archetype / Platonic-form view

A very abstract map can show recurring meal forms.

Example nodes:

- protein + rice + aromatic liquid
- protein + marinade + dry heat
- paste + coconut milk + protein
- tomato base + protein + simmer
- egg + tangy dairy + bread
- soft tofu + spicy broth + egg

Then actual dishes hang underneath as regional manifestations.

This is one of the strongest educational views because it makes global variation intelligible.

---

# 14. Geographic coincidence view

Overlay one structural family on a literal world map.

Example:

> **one-pot chicken + rice**

Pins / regions:

- Puerto Rico — arroz con pollo
- Brazil — galinhada
- Trinidad — pelau
- Somalia — bariis iskukaris
- Arabian Peninsula — kabsa / mandi
- Hainan / Singapore — chicken rice family

The UI should label this:

> **structural neighborhood — not necessarily historical lineage**

Then if documented influence exists, a separate provenance layer can be toggled on.

---

# 15. Heatmaps

Potential heatmaps:

### My food map

Color intensity = number of cooks / ratings.

### Ingredient reachability

Color = how many current pantry ingredients overlap.

### Novelty

Color = distance from recent eating history.

### Friend overlap

Color = dishes / techniques shared with selected friend.

### Cuisine underexploration

Color = nearby cuisines with many reachable but untried dishes.

---

# 16. “Take me somewhere” animation

User presses:

> **Take me somewhere**

The map could zoom / pan from current kitchen to a selected destination.

Example:

`chicken thighs`
→ `one new purchase: Caribbean green seasoning`
→ map travels to Trinidad
→ highlights pelau + curry chicken
→ user picks pelau

The transition itself reinforces the “vacation” metaphor.

---

# 17. Shopping unlock animation

Tap:

`Buy gochujang`

Watch new nodes illuminate:

- gochujang chicken
- dakbokkeumtang
- spicy noodles
- salmon glaze
- bibimbap-ish rice bowl

This makes a grocery purchase feel like unlocking a region of a game map.

---

# 18. Pantry constellation

Instead of a checklist of inventory, render high-leverage ingredients as a constellation.

Large / bright nodes:

- gochujang
- miso
- sambal
- curry paste
- sofrito
- tahini

Node size can represent current unlock value for the user.

This can answer:

> **Which jar in my fridge is currently doing the most work?**

---

# 19. Social graph-diff view

Compare two users.

Views:

### Shared territory

What both have cooked.

### Your frontier

Things you know that they do not.

### Their frontier

Things they know that you do not.

### Same destination, different routes

Both cooked adobo, but with different implementations.

### Bridge nodes

Ingredients / techniques that connect the two graphs.

This makes recipe sharing targeted and personal.

---

# 20. Regional deep zoom

Geography should support tiny-scale discovery where data quality allows.

Possible zoom hierarchy:

- continent
- country
- region / state / province
- city
- town / island / community

A user could discover:

> “This neighboring region has a rice dish with the same base but a completely different souring ingredient.”

The app should preserve uncertainty and source quality.

Do not manufacture hyperlocal claims without evidence.

---

# 21. Temporal map

Later, documented history could add a time slider.

Possible views:

- when an ingredient entered a region
- migration / diaspora branches
- documented publication history of a dish name
- historical variants

This requires serious sourcing and should be clearly separated from morphological similarity.

Potentially amazing, but far beyond MVP.

---

# 22. UI performance principle: local neighborhoods

Hairball prevention rule:

> never render every edge.

Show:

- local neighborhood
- strongest relationships
- user-selected layers
- semantic clustering

Progressively reveal detail as the user interacts.

The graph should feel like a map, not a network-science debugging screen.

---

# 23. Mobile-first interaction

This whole product is especially suited to phone use.

Gestures:

- pinch to semantic-zoom
- tap node to re-center
- long-press ingredient to see substitutes
- swipe dish to compare nearest alternatives
- drag one node onto another to preview a merge
- tap `fork` to copy path
- tap `diff` to compare implementations

The phone should feel like a culinary map in the user's hand while cooking happens around them.

---

# 24. The map should teach without lecturing

The interface can create cooking literacy through repeated visual exposure.

The user gradually learns:

- what a braise family looks like
- what curry paste replaces
- what ingredients travel together
- how different rice traditions relate structurally
- where a substitution changes identity strongly
- what kinds of dishes are naturally batchable

The user learns by navigating.

---

# Current thesis

The product should feel like **Google Maps + a tech tree + version history + a culinary atlas**, without becoming visually overwhelming.

The key is multiple views of the same underlying graph:

- geographic
- morphological
- flavour
- workflow
- personal
- social
- provenance

A recipe card is still useful when it is time to cook.

But discovery should happen on the map.