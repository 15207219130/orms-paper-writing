# Ingredients for the Introduction — joint assortment & inventory for quick-commerce dark stores

Target journal: **Management Science**. I need the **Introduction** drafted (hook, gap, an explicit
contributions paragraph, and a roadmap). Here are the raw ingredients.

## Topic / setting
Quick-commerce platforms (e.g. 15-minute grocery delivery) operate small urban "dark stores"
(micro-fulfillment centers) with very limited shelf space. Each dark store must choose, for each day,
which subset of SKUs to stock (assortment) and how many units of each (inventory), under tight space
and short replenishment cycles. Customers substitute to other products when their first choice is out
of stock or not carried. Demand is highly local and time-varying. The platform wants to maximize
expected profit (margin × sales − holding/wastage − lost-sales), accounting for substitution.

## Why it's hard / what's new (my notes)
- assortment and inventory are usually studied separately; here they're coupled through shared shelf
  space and through stock-out-based substitution (dynamic substitution depletes inventory and
  redirects demand)
- the dark-store space constraint is binding and couples SKUs (unlike classic newsvendor per-SKU)
- demand is local + nonstationary; we use a choice model (MNL-ish) estimated per store-daypart
- existing assortment work mostly assumes ample inventory or static substitution; existing joint
  models don't handle the space-coupling + perishability of groceries

## My three contributions (rough)
1. We formulate a joint assortment-and-inventory model for space-constrained micro-fulfillment with
   dynamic (stock-out-based) consumer substitution and perishability — first to combine these.
2. We characterize structural properties of the expected-profit function (some concavity /
   submodularity-like structure) and use them to design an efficient algorithm with a performance
   guarantee.
3. Using data from a real quick-commerce operator, we show the joint policy lifts profit ~6–9% over
   stocking by observed demand, with larger gains for smaller stores / more substitutable categories;
   we derive managerial guidance on which stores benefit most.

## Key results to preview
- structural result enables an algorithm that scales to thousands of SKUs per store
- empirical: 6–9% profit lift; "stock breadth over depth" insight for highly substitutable
  categories; the value of joint optimization rises as shelf space tightens

## Stuff for the hook
- quick-commerce is a big, fast-growing market; dark stores have tiny footprints so every shelf slot
  is contested; out-of-stocks are common and customers substitute or abandon. (I don't have exact
  market-size figures handy — if you want to cite a number, flag that I need to find/verify it.)

Write it like a Management Science paper: lead with the managerial relevance, motivate with real
stakes, make the gap and contributions mirror each other, end with a section roadmap. Sections will
be: 2 lit review, 3 model, 4 structure+algorithm, 5 estimation, 6 numerical/case study, 7 conclusion.
