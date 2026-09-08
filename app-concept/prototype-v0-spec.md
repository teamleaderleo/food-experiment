# Food Pathfinder v0 — Smallest Mathematically Coherent Prototype

**Status:** implemented as a static prototype in [`../prototype/index.html`](../prototype/index.html).

The goal of v0 is not to approximate the final product. It is to answer one narrower question:

> **Does representing food as a navigable graph produce genuinely fun and useful behavior before we add scale?**

---

## Scope lock

The prototype intentionally stops at:

- **36 dish paths**
- **58 tracked ingredient / flavour-asset nodes**
- a small set of cooking-method classes
- approximate geography
- one morphology embedding
- one inventory state
- one transparent route-cost model
- one-purchase unlock ranking
- ingredient lens
- nearest structural neighbors

No authentication.  
No backend.  
No LLM generation.  
No nutrition engine.  
No grocery-price API.  
No social graph.  
No historical-influence claims.  
No automatic recipe scraping.

Those are later problems.

---

## Graph model

For v0, a dish path is represented as:

```text
Dish d = {
    requirement set R_d,
    method,
    meal family,
    protein class,
    starch class,
    geography,
    effort vector,
    morphology coordinates
}
```

The full eventual system is a directed hypergraph, but a requirement-set representation is sufficient to test the first cartographic interactions.

### Ingredient reachability

For inventory `I`:

```text
M_d = R_d \ I
```

Then:

```text
|M_d| = 0  -> Here now
|M_d| = 1  -> One unlock away
|M_d| >= 2 -> Farther away
```

This is intentionally discrete and legible.

---

## Morphology space

The prototype uses 2D coordinates precomputed from a PCA-style feature embedding built from:

### Categorical features

- meal family
- cooking method
- protein class
- starch class

### Numerical flavour features used when the seed coordinates were built

- acidity
- heat
- sweetness
- creaminess
- fermented / savory character
- aromatic intensity
- tomato intensity
- coconut intensity
- smoky / char character

The resulting 2D coordinates are a visualization convenience, not a statement that food truly lives in two dimensions.

The useful behavior is:

> dishes near each other should often produce a plausible **“wait, those are cousins in cooking-form”** reaction.

Morphological proximity means resemblance, not ancestry or historical influence.

---

## Geography space

Geographic view uses approximate latitude / longitude reference points.

This layer asks:

> **Where is this dish associated with?**

Morphology asks:

> **What does this dish resemble as a cooking object?**

Switching between them is the first proof that the same culinary dataset can support multiple coordinate systems.

---

## Route cost

The first cost function is deliberately crude and inspectable:

```text
C(d) =
    8 * missing(d) * w_purchase
  + 0.14 * active_minutes(d) * w_active
  + 1.55 * attention(d) * w_attention
  + 1.25 * cleanup(d) * w_cleanup
  - 0.68 * leftovers(d) * w_leftovers
  - 0.62 * phone_compatibility(d) * w_phone
```

Lower is better.

The coefficients are disposable.

What should survive is the idea that **different users assign different edge costs to the same cooking path**.

A person who enjoys chopping should not get the same recommendations as a person who hates it. A 70-minute oven dish can be easier than a 20-minute stir-fry when the oven dish has only a few attention spikes.

---

## One-purchase optimization

For every ingredient `i` not currently owned, simulate:

```text
I' = I union {i}
```

Then calculate:

```text
new_complete(i)
new_one_away(i)
```

The v0 ranking is:

```text
U(i) = 10 * new_complete(i) + new_one_away(i)
```

This is the first implementation of:

> **What one purchase expands my food world the most?**

Later versions can add:

- price
- shelf life
- expected liking
- nutrition
- ingredient redundancy
- cuisine novelty
- perishability
- multi-purchase set-cover optimization

---

## Why some nodes are bundled assets

A strict raw-ingredient ontology makes the graph explode before the interaction model has been validated.

So v0 includes nodes such as:

- `inasal_marinade`
- `japanese_dashi_sauce`
- `green_seasoning`
- `bariis_spice`
- `jollof_base`
- `moroccan_lemon_olive`
- `south_indian_tempering`

These are not claims that the components are indivisible. They are **collapsed subgraphs**.

If a node becomes interesting, a future UI can zoom into it:

```text
green seasoning
↓
culantro
scallion
thyme
garlic
chile
acid
...
```

This gives the product a natural semantic-zoom model.

---

## What the runnable prototype tests

### 1. Geography ↔ morphology

The same dish nodes move between two coordinate systems.

### 2. Inventory reachability

Checking or unchecking an ingredient immediately changes which meals are green, amber, or gray.

### 3. One-purchase marginal graph expansion

The app ranks missing ingredients by how much of the graph they unlock.

### 4. Personal friction weights

The route ranking changes when purchases, active time, attention, cleanup, leftovers, or phone compatibility are weighted differently.

### 5. Bottom-up ingredient lens

Select one ingredient and the map dims every dish that does not use it.

That is the first primitive version of:

> **Show me how this ingredient radiates through the world.**

---

## The v0 magical moment

Use the default kitchen.

1. Notice several dishes are already reachable.
2. Switch geography → morphology.
3. Watch geographically distant foods move near one another.
4. Select an ingredient such as coconut milk and see its constellation.
5. Click one of the recommended one-purchase unlocks.
6. Watch several nodes change reachability immediately.

If that sequence feels compelling, the representation is doing real product work.

---

## Success criteria

The prototype succeeds if a person naturally does at least a few of these:

- switches geography → morphology just to see where dishes move
- notices two dishes they had never mentally connected
- toggles one ingredient and thinks “holy shit, that unlocks all of those”
- changes friction weights and gets recognizably different recommendations
- follows an ingredient lens across distant regions
- clicks through structural neighbors without needing a recipe search box

If none of that is fun at 36 dishes, adding 36,000 dishes will not fix the product.

---

## Next mathematical step

If v0 passes the fun test, the next prototype should add **time and state**.

Current v0:

```text
inventory -> dish
```

Next:

```text
state_t
  -> cooking action
  -> dinner
  -> leftovers / reusable assets
  -> state_t+1
```

That adds:

- intermediate nodes
- yield
- storage
- expiration
- leftovers
- future option value
- multi-day planning

At that point route selection becomes a sequential decision problem rather than a static ranking problem.

That is where the deeper planning math starts earning its keep.
