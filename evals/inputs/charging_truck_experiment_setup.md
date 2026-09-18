# Experimental setup + raw results — mobile EV charging truck dispatch

I need the **Numerical Experiments / Computational Study section** written for an Operations Research
submission. This is the same project as the mobile charging-truck dispatch model (team-orienteering
with time windows + energy capacity). Here are my setup notes and raw results.

## What I want the experiments to show / questions
1. Is our branch-and-price (B&P) algorithm fast enough vs. solving the MILP directly in Gurobi?
2. How much does serving with mobile charging trucks (our optimized policy) beat simple dispatch
   rules a real operator might use?
3. How do results change with fleet size, demand density, and time-window tightness?
4. (robustness) what happens when energy needs are uncertain vs. our deterministic plan?

## Instances
- Synthetic instances on a 20km×20km grid; requests drawn from a mixture of hotspots (mimicking
  downtown + residential). Sizes n = 20, 50, 100, 200 requests; |K| trucks = 2, 4, 8.
- Time windows generated with width drawn from {30, 60, 120} min ("tight/medium/loose").
- Also a real-data case: one month of EV charging-session data from a mid-size Chinese city (an
  industry partner; ~12,000 sessions), aggregated to daily request sets. Locations are real;
  energy needs from session kWh.
- Solver: Gurobi 11.0; machine: 16-core 3.5GHz, 64GB RAM. Code will go in an online companion.

## Benchmarks / baselines
- MILP-direct: hand the full MILP to Gurobi with a 1-hour limit.
- Greedy-nearest: each truck repeatedly takes the nearest feasible request.
- Zone-based: partition the city into |K| zones, one truck per zone, solve each small.
- (these are meant to be reasonable operator heuristics, not straw men)

## Raw results (rough numbers)
- B&P solves n≤100 to optimality in < 60s on average; MILP-direct only solves n≤50 within the hour,
  and at n=100 MILP-direct has an average 14% optimality gap remaining.
- At n=200 B&P doesn't always close the gap but returns solutions within ~3% of best bound in 10 min.
- Our policy vs Greedy-nearest: +18% served-revenue on average (range +9% to +27%); biggest gains
  when time windows are tight and demand dense.
- Our policy vs Zone-based: +7% on average; zone-based is closer when demand is spatially uniform but
  much worse under hotspots.
- Real-data case: our policy serves 22% more sessions than the operator's current near-greedy
  practice at the same fleet size; or equivalently serves the same demand with 2 fewer trucks.
- Robustness: when actual energy needs exceed the deterministic estimate by up to 15% (random), the
  deterministic plan becomes infeasible/under-delivers on ~11% of routes; a simple energy-buffer
  (reserve 10% of Q) restores feasibility with only ~2% revenue loss. (Full robust model is future
  work — just report this sensitivity.)

## Notes
- Fleet size: diminishing returns — going 2→4 trucks helps a lot, 4→8 less so; I want a figure.
- I want managerial takeaways: when is the mobile-charging service most valuable? (tight windows,
  dense/hotspot demand, moderate fleet). And the energy-buffer practical tip.
- Be honest that the deterministic model has limits (the robustness bit), don't oversell.

Write it as a proper OR numerical-study section.
