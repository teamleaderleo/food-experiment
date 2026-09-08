# Food Pathfinder — Mathematical Model

**Status:** product / research notes

Food Pathfinder is interesting because the core problem is not merely recipe recommendation. It is a combination of:

- graph theory
- hypergraph search
- multi-objective optimization
- scheduling
- state-transition planning
- set cover / maximum coverage
- similarity geometry / embeddings
- preference learning
- geographic visualization

The app can begin with simple heuristics and become more sophisticated only where the extra math improves the user's decisions.

---

# 1. The base object: a typed directed hypergraph

A recipe step often consumes several things and produces a new thing.

Example:

`chicken thighs + fish sauce + sugar + ginger`

passed through:

`12-minute braise`

produces:

`Vietnamese caramel chicken`

A simple graph edge from one node to another does not represent this naturally. A directed hyperedge does:

> **multiple input nodes -> one operation -> one or more output nodes**

Useful node types:

- raw ingredients
- pantry flavour assets
- aromatic bases
- prepared leftovers
- intermediate food states
- finished dishes
- techniques / operations
- equipment
- cultural dish-family nodes
- geography nodes
- users / personal implementations

Useful edge types:

- transforms
- combines-with
- substitutes-for
- commonly-served-with
- culturally-associated-with
- derived-from / adapted-from when documented
- morphologically-similar-to
- owned-by / available-to-user
- cooked-by-user
- forked-from

The graph should keep **historical lineage edges** separate from **structural similarity edges**.

---

# 2. Cost is a vector, not one number

The user does not have one universal definition of “easy.”

A candidate path has several costs:

`c(path) = [shopping, money, active time, attention, chopping, cleanup, perishability, technique risk, elapsed time]`

and several rewards:

`r(path) = [expected taste, novelty, leftover value, nutrition fit, guest payoff, cultural interest, ingredient reuse]`

Different users assign different weights.

For this project's current preference profile:

- chopping cost is high
- raw-meat / sticky-bowl hand-fuss is high
- unattended oven / braise time is low cost
- buying a good prepared condiment can be low cost
- leftover value is strongly positive

Do not force everything into a scalar too early.

A good UI can expose a **Pareto frontier**:

> these are the meals for which no alternative is simultaneously cheaper, less fussy, and more appealing.

Then the user chooses which tradeoff sounds good tonight.

---

# 3. Culinary distance

Define the distance from the current kitchen state to a dish or path.

A first heuristic:

`distance = purchases + effort + technique novelty + cleanup + perishability`

with personalized weights.

Possible labels:

- **Here now**
- **One unlock away**
- **Easy detour**
- **Weekend expedition**

Distance can be asymmetric.

Going from:

`plain rice -> lemon rice`

may be very cheap if curry leaves / mustard seeds are already owned.

Going from:

`lemon rice -> plain rice`

is trivial, but the interesting direction is the one that creates novelty.

---

# 4. Multi-objective shortest paths

The app's central query is a pathfinding problem:

> Given current inventory and constraints, find useful routes to desirable meals.

This is not always ordinary Dijkstra because edge weights are vectors and user preferences vary.

Practical early implementation:

1. filter impossible paths
2. calculate a weighted heuristic score
3. keep several Pareto-efficient alternatives
4. explain why each path is attractive

Later possibilities:

- A* with an admissible rough culinary-distance heuristic
- multi-objective Dijkstra
- constrained shortest path
- k-shortest paths so the user sees alternate routes to the same dish

That last one is especially important:

> **Love the destination; dislike this route.**

Search for another route.

---

# 5. Recipe execution is a scheduling problem

A recipe is not merely an ordered list.

Many operations happen in parallel.

Example baseline:

- rice cooker runs
- air fryer runs
- garlic is grated near the end
- wing flip occurs once

This is a **directed acyclic graph of tasks** with dependencies and resource constraints.

Each operation can have:

- active duration
- unattended duration
- required equipment
- required hands / attention
- earliest start
- dependency set

Then the app can calculate:

- critical path
- total elapsed time
- actual hands-on time
- periods of free attention
- equipment collisions
- moments where two high-attention steps overlap

This directly models **phone compatibility**.

A 45-minute meal may have only 7 minutes of occupied attention distributed across four short bursts.

That is a much better representation than a recipe website saying `45 minutes`.

---

# 6. Attention occupancy

A useful time-dependent model:

`a(t) in [0,1]`

where:

- 0 = completely unattended
- 0.2 = glance / occasional stir
- 0.6 = regular monitoring
- 1 = hands occupied / cannot disengage

Then derive metrics like:

- total active-attention area under the curve
- longest uninterrupted free-attention window
- number of attention interruptions
- maximum simultaneous attention demand

This could explain why:

- a braise feels easy
- a 15-minute stir-fry feels demanding

Even when the braise takes much longer on the clock.

---

# 7. Leftovers turn dinner planning into a state-transition problem

Cooking changes tomorrow's graph.

State at time `t` might include:

- raw inventory
- leftovers
- marinated bags
- prepared aromatic cubes
- cooked sauces
- expiration risk
- user's recent cuisine history

A cooking action changes that state.

This resembles a **Markov decision process / planning problem**:

`state_t + cooking_action -> meal + state_(t+1)`

Example:

Tonight:

`large pot of adobo`

produces:

- dinner now
- 2 portions adobo
- possibly seasoned braising liquid

Tomorrow's reachable meals are therefore different.

The optimal meal tonight may be slightly more work because it creates very valuable future states.

That is why independent one-night recipe ranking is insufficient.

---

# 8. Shopping as maximum coverage / set cover

Question:

> What 3–5 purchases unlock the largest useful part of the graph?

This is close to **maximum coverage** under a budget.

Each candidate ingredient unlocks a set of dish paths.

Example:

`lemongrass paste`

may unlock:

- Vietnamese lemongrass chicken
- chicken inasal
- Thai curry branches
- Sri Lankan curry
- coconut noodle soups

But raw unlock count is too naive.

Weight unlocked dishes by:

- probability user would enjoy them
- existing ingredient overlap
- shelf life
- novelty
- low-fuss compatibility
- whether other purchases are still required

Then optimize:

> maximize useful culinary territory unlocked per dollar / perishable item / pantry slot.

This is a mathematically interesting version of grocery planning.

---

# 9. Ingredient importance should be inverse-frequency weighted

Salt, oil and water appear everywhere and are poor signals of cuisine similarity.

A useful analogy is TF-IDF.

For ingredient `i` in dish `d`:

- high weight if ingredient is characteristic of the dish
- lower global weight if it appears in nearly every recipe

So:

- salt -> near-zero identity weight
- chicken -> modest structural weight
- pandan -> high identity weight
- berbere -> high identity weight
- pomegranate molasses -> high identity weight

This improves clustering and similarity search.

---

# 10. Morphology space vs flavour space

Two dishes can be similar in different coordinate systems.

### Morphology space

Features:

- protein type
- starch type
- one-pot vs separate
- dry heat vs braise vs soup
- sauce richness
- texture
- serving format
- task DAG / workflow pattern

Arroz con pollo, pelau, bariis and kabsa may sit near each other here.

### Flavour space

Features:

- acid / salt / sweet / heat / bitter / umami
- dominant aromatics
- fat medium
- spice families
- fermented ingredients
- fresh herb load

### Geography space

Literal map coordinates / region hierarchy.

### Provenance space

Documented relationships, sources, household variants, migrations, adaptations.

The app should let users switch coordinate systems rather than pretending one distance metric explains everything.

---

# 11. Embeddings and dimensionality reduction

Once enough structured recipes exist, each dish/path can be embedded into a high-dimensional feature space.

Then visualization can use:

- PCA for interpretable global axes
- UMAP for neighborhood visualization
- t-SNE cautiously for local exploration
- graph embeddings for topology-aware similarity

The UI should not imply that a 2-D map is objective truth.

It is a projection of one chosen similarity model.

That can itself be fun:

- switch to workflow projection
- switch to flavour projection
- switch to ingredient projection

Watch the culinary world rearrange.

---

# 12. Community detection

Graph clustering can identify emergent families without hard-coding them.

Possible methods:

- Louvain / Leiden communities
- spectral clustering
- hierarchical clustering

Clusters might reveal:

- coconut-curry neighborhood
- soy-vinegar braises
- tomato-rice one-pot dishes
- fermented-chile + rice bowls
- yogurt/egg/bread meals

The interesting question is where algorithmic clusters agree with culinary intuition and where they reveal unexpected neighborhoods.

---

# 13. Graph edit distance / recipe diffs

A fork is a graph edit.

Operations might be:

- add ingredient
- remove ingredient
- substitute ingredient
- change ratio
- change operation
- reorder operation
- swap equipment
- change serving format

Then two recipe paths can have a meaningful diff cost.

This can support:

- “nearest shortcut version”
- “closest vegetarian fork”
- “lowest-fuss implementation that preserves flavour identity”
- “show me how my version differs from the reference path”

---

# 14. Preference learning

The app should learn from actual cooks, not abstract likes.

Observed signals:

- taste rating
- repeat / no-repeat
- substitutions kept or reverted
- cleanup complaint
- unfinished leftovers
- how soon dish is cooked again
- path forked again

Simple early model:

- per-user weighted linear scoring

Later:

- Bayesian preference model
- contextual bandits for exploration vs familiar recommendations
- pairwise ranking from “which would you rather cook tonight?”

Crucial constraint:

> preserve exploration.

A recommender that only repeats known favorites destroys the map-discovery experience.

Novelty should be an explicit reward.

---

# 15. Geography without false ancestry

Each dish / variant can have geographic metadata:

- country
- region
- city / town / community when appropriate
- diaspora locations

Then the user can render structural similarity over geography.

Interesting query:

> Show all one-pot chicken-and-rice dishes on a world map.

The map may reveal visually similar solutions across distant places.

But geographic proximity or structural similarity should never be displayed as proof of influence.

If documented historical connections exist, show them as a **different edge layer** with citations.

---

# 16. A surprisingly deep optimization problem: pantry design

Question:

> With 25 shelf/fridge/freezer slots, what inventory maximizes my reachable high-rated food space?

This resembles constrained facility-location / portfolio optimization.

Inputs:

- ingredient shelf life
- cost
- storage footprint
- number / quality of meals unlocked
- cuisine diversity
- redundancy
- user preferences

Output:

A pantry designed for **option value**, not merely ingredient count.

A jar of gochujang is valuable partly because it creates many future routes.

---

# 17. The central mathematical object may be option value

An ingredient or prepared asset has value beyond the meal it enters tonight.

Its value is partly:

> how many desirable future paths does possessing this node make reachable?

That is why:

- a flexible sauce can be more valuable than a single-use ingredient
- leftover rice is valuable
- marinated chicken bags are valuable
- master sauce is valuable
- epis cubes are valuable

Cooking is partly the creation and consumption of future option value.

---

# Current thesis

Food Pathfinder can begin with simple rules, but the underlying problem is genuinely rich:

> **navigate a personalized, time-evolving, multi-objective hypergraph of food transformations.**

The math is useful because it corresponds directly to real questions:

- What can I make?
- What should I buy?
- What route is easiest for me?
- What should I cook tonight if tomorrow counts too?
- What cuisines are structurally near something I already know?
- What new region can one jar unlock?
- Which shortcut preserves the most of what I like?

That is enough mathematical depth to support years of product experimentation without requiring the first version to be complicated.