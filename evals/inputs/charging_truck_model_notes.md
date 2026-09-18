# Rough model notes — mobile EV charging truck dispatch (for an Operations Research submission)

These are my messy notes. I need the **Model / Formulation section** written up.

## Setting (rough)
A service provider runs a fleet of mobile charging trucks. EV drivers in a city open an app and
submit charging requests over a day. Each request has a location, a time window, and an energy
amount. Trucks have limited battery capacity (they store energy and deliver it), and must return to a
depot to recharge themselves. We decide which truck serves which request and in what order (routing),
and we want to maximize served demand / profit minus travel and penalty costs. Planning is for one
operating day, demand is uncertain but assume we solve a deterministic version first then mention a
robust/stochastic extension.

## Symbols I've been using (inconsistent, please clean up)
- requests i = 1..n ; trucks k in K ; depot is node 0
- each request: location, energy need e_i, time window [a_i, b_i], revenue r_i if served
- truck capacity Q (energy it can carry), travel time t_ij between nodes, energy used to travel?
  (ignore truck's own driving energy for now, or mention as assumption)
- x_{ijk} = 1 if truck k goes from i to j ; y_{ik}=1 if truck k serves request i
- service time at request s_i
- arrival time variable T_{ik}
- penalty p_i if request i not served
- big-M somewhere for time/subtour stuff

## Objective
max revenue from served requests minus travel cost minus unserved penalties. (cost per unit travel
time c.)

## Constraints I know I need
- each request served at most once (by at most one truck)
- flow conservation / routing for each truck, start and end at depot
- truck energy capacity: total energy delivered on a route <= Q
- time windows: arrival within [a_i,b_i]; time propagation along route (MTZ-style or big-M)
- subtour elimination
- linking x and y

## Notes / things to mention
- it's a team-orienteering-problem-with-time-windows variant basically
- assume service times deterministic; assume trucks identical; assume one recharge of the truck at
  depot only (no mid-route swap) — actually maybe allow returning to depot to reload energy? I'm
  unsure, pick the cleaner option and state the assumption.
- I'll add robustness on demand/energy later, just set up the deterministic core cleanly.

Please write this as a proper Model section for an OR paper. Use whatever notation is cleanest and
internally consistent — fix my inconsistencies. I want it to read like a top journal.
