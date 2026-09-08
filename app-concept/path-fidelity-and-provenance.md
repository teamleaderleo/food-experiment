# Path Fidelity, Provenance + Variant Identity

**Status:** product concept notes

Food Pathfinder should let people branch aggressively without pretending that every branch is still the same dish.

The graph needs to distinguish:

- the **dish family / cultural reference point**
- a **specific implementation path**
- the **user's modified path**
- the user's **rating of that path**
- the degree to which the result still preserves the identity of the reference dish

This prevents the app from flattening cuisines into generic “protein + sauce” templates while still making experimentation fun.

---

## 1. Dish family vs implementation

Example:

**Chicken adobo** is a dish family / reference node.

Possible implementations:

- bone-in traditional-style braise
- boneless-thigh shortcut
- pressure-cooker version
- sweeter household variant
- coconut-adobo regional variant

These are not merely comments on one recipe. They are separate paths connected to the same cultural family.

The app should preserve both levels.

---

## 2. Fidelity is multidimensional

A shortcut can preserve some parts of a dish and change others.

Possible fidelity dimensions:

- core flavour balance
- key technique
- texture
- characteristic ingredients
- serving format
- cultural / regional lineage

Example:

**Vietnamese lemongrass chicken, air-fryer shortcut**

- flavour fidelity: high
- technique fidelity: medium
- texture fidelity: high enough
- workflow gain: very high

That is more useful than declaring it simply “authentic” or “inauthentic.”

---

## 3. Show the branch point explicitly

A user should be able to see:

`reference path`
→ **branch here**
→ `shortcut / substitution`
→ `result`

Example:

`fresh lemongrass, finely chopped`
→ **swap**
→ `lemongrass paste`

The app can say:

- preserves flavour well
- removes chopping
- small texture/aroma loss
- highly recommended for weekday use

The user understands exactly what changed.

---

## 4. Rate implementations separately from dishes

A user may think:

- dish concept: 10/10
- this implementation: 6/10
- cleanup: terrible
- flavour: amazing
- would retry using another path

That should create a signal like:

> **Love the destination; dislike this route.**

Then the recommender searches for another path to the same dish family rather than concluding that the user dislikes the food.

---

## 5. Provenance should travel with graph nodes

Culturally specific dishes should retain source context.

Useful metadata:

- country / region
- subregion / community when known
- household / restaurant / author source
- original external recipe link
- notes on major traditional variants
- whether the current path is traditional, adapted, shortcut, fusion, or experimental

The point is not purity policing.

The point is that exploration is more fun when the map tells you where an idea came from.

---

## 6. Variant maps could be beautiful

A dish page could show a local graph around one family.

Example: **adobo**

- Filipino chicken adobo
  - bone-in braise
  - boneless weekday path
  - coconut-milk branch
  - pressure-cooker branch
  - leftover-fried-rice branch

Or **curry** as a huge network where Thai red curry, Malaysian kari ayam, Sri Lankan chicken curry, Japanese curry, Trinidad curry chicken and Indian butter chicken are related at higher-level motifs but remain clearly distinct cultural nodes.

---

## 7. Personal maps become more meaningful

Instead of only saying:

> You cooked 14 chicken dishes.

The app can say:

- 5 Ziploc + dry-heat paths
- 4 braises
- 3 one-pot rice paths
- 2 curry-paste paths
- strongest region: East / Southeast Asia
- newest region: Caribbean
- most repeated technique: air fryer
- highest-rated shortcut: lemongrass paste for Vietnamese chicken
- dish family you love but have not found a low-fuss route for yet: mujadara

That is actual culinary self-knowledge.

---

## 8. Social comparison becomes graph diff

Compare two users by:

- overlapping dish families
- different implementations of the same dish
- techniques one knows that the other has not tried
- identity ingredients owned by one but not the other
- regions explored
- shortcut acceptance
- rating differences

A great social prompt becomes:

> **You both love chicken curry. Alex reaches it through Thai red curry paste; you reach it through Sri Lankan roasted curry powder. Swap paths this week.**

---

## 9. “Fork this path” is the natural social action

Instead of only Like / Save / Repost:

> **Fork path**

A fork copies someone else's cooking route into the user's graph and lets them change nodes.

Example:

Friend's path:

`chicken thigh + jerk marinade -> air fry -> rice + pineapple salsa`

User forks it:

`salmon + jerk marinade -> air fry -> coconut rice + bought pico`

Both remain linked, so the lineage of the idea is visible.

This is much more interesting than copying a recipe card.

---

## 10. The social artifact

A shareable card / animation could show:

**START**

chicken thighs + rice + yogurt

↓ add: sumac + lemon

↓ marinate in bag

↓ air fry

↓ add bought pickled onions + yogurt sauce

**RESULT: sumac chicken rice**

Rating: 9/10  
Hands-on: low  
Would repeat: yes  
Branch note: skipped fresh herbs; no meaningful loss

Then beneath it:

> **Fork this path**

That is the product's version of a social post.

---

# Current thesis

The global graph should preserve **where food comes from**.

The personal graph should preserve **how the user actually got there**.

The social graph should preserve **who forked whose path and what changed**.

That creates a system where experimentation, cultural context, convenience and community reinforce each other rather than compete.
