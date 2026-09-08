# Recipe Version Control — Forks, Diffs, Merges + Lineage

**Status:** product concept notes

The `fork` metaphor is unusually strong because recipes already evolve this way in real life.

A dish is learned from a household, restaurant, cookbook, region, friend, video, or memory. Then someone changes:

- an ingredient
- a ratio
- a cooking vessel
- a timing step
- the protein
- the starch
- the level of heat
- a shortcut
- the serving format

That changed implementation is effectively a **forked path**.

The app can make this existing human behavior visible without pretending culinary traditions are software repositories.

---

## 1. Fork

A fork starts from an existing path and creates a linked personal branch.

Example:

`Vietnamese lemongrass chicken`

reference path:

`fresh lemongrass + thigh -> marinate -> grill -> vermicelli/herbs`

weekday fork:

`lemongrass paste + thigh -> bag marinade -> air fryer -> rice`

The fork should retain:

- parent path
- source / provenance
- what changed
- rating
- workflow gain/loss
- flavour / texture impact

---

## 2. Diff

The app should be able to show a human-readable diff between two cooking paths.

Example:

### Parent

- fresh lemongrass
- grill
- rice noodles
- fresh herb salad

### Fork

- lemongrass paste
- air fryer
- white rice
- bought pickles

### Effect

- chopping: much lower
- active time: lower
- smoke/char: lower
- flavour identity: largely preserved
- repeatability: much higher for this user

This is far more useful than a comment saying “I changed a few things.”

---

## 3. Commit / cook log

Every actual cook can be a lightweight commit to the personal graph.

Example:

> **Cooked Vietnamese caramel chicken v3**
>
> - used 320 g boneless thigh
> - doubled ginger
> - reduced sugar slightly
> - cooked 2 minutes longer to glaze
> - 9/10
> - cleanup excellent
> - repeat this version

The point is not software cosplay. The useful idea is preserving **what actually happened** so the user's successful implementation stops disappearing into memory.

---

## 4. Branch

A dish family can contain many legitimate branches.

Example: adobo

- household A: vinegar-forward
- household B: sweeter
- coconut-adobo branch
- bone-in branch
- boneless weekday branch
- pressure-cooker branch
- leftover fried-rice branch

Some branches may have cultural / regional lineage; others are personal experiments.

The graph should label the difference rather than collapse everything into one canonical recipe.

---

## 5. Merge

Cooking constantly merges ideas from different paths.

Example:

- take jerk chicken marinade from one path
- take nasi-le-mak coconut rice from another
- add bought pico from a third convenience system

Result:

`jerk salmon + coconut rice + pico`

This is a fusion / experimental merge, and the graph can show exactly which components came from where.

A merge does not imply the result is a traditional dish. Provenance labels keep that clear.

---

## 6. Cherry-pick

Sometimes the user does not want the whole recipe. They want one high-value idea.

Examples:

- cherry-pick the yogurt sauce from one dish
- cherry-pick the pickled-onion finisher from another
- cherry-pick the rice-cooker method
- cherry-pick the spice blend
- cherry-pick the 12-minute caramel-braise technique

This may be one of the most useful interactions in the app:

> **Add this component to my toolkit.**

The user's personal graph gains the reusable node without needing to save the entire dish.

---

## 7. Revert

A failed experiment should be useful data.

Example:

> v4 replaced chicken thigh with breast.
> Result: too dry.
> Revert to thigh branch.

The app should make failure cheap and informative rather than treating every cook as a permanent recommendation.

---

## 8. Stable version / personal canonical path

After several cooks, one path may become the user's preferred implementation.

Example:

> **My default adobo**
>
> boneless thighs + 1:1 soy/vinegar-ish base + garlic paste + bay + pepper -> braise -> rice

That becomes the personal stable branch.

A more traditional / guest / weekend branch can still coexist.

---

## 9. Compare forks socially

A dish page could show:

> 842 people cooked this family.
>
> Most common weekday forks:
> - air fryer instead of grill
> - prepared aromatics
> - boneless thigh
> - bought pickles
>
> Highest-rated flavour-preserving shortcut:
> - lemongrass paste
>
> Highest-rated guest path:
> - charcoal grill + fresh herb bowl

This surfaces collective practical knowledge without reducing everything to star ratings.

---

## 10. Fork lineage can tell stories

A recipe path can carry a lineage like:

`regional / household source`
→ `published recipe`
→ `friend's adaptation`
→ `my weekday fork`
→ `my salmon fork`

That is both technically useful and socially meaningful.

It lets a person say:

> **This is the path I inherited, this is the part I changed, and this is the version I actually cook.**

---

# Important caveat

Food traditions are not software repositories.

Cuisines evolve through communities, migration, trade, scarcity, family memory, restaurants and parallel invention. Many dishes do not have a single clean ancestor.

So the app should use version-control ideas for **implementation lineage**, while keeping cultural provenance richer and less falsely linear.

The metaphor is a tool for understanding and sharing paths, not a claim that cuisine history behaves like Git.

---

# Current thesis

The killer social action may genuinely be:

> **Fork this path.**

Then the app records the diff.

That turns recipe modification from an invisible private act into something explorable, comparable and teachable.

People already fork recipes.

Food Pathfinder would finally let them see the tree.