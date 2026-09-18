# Draft literature review to revise — drone-assisted last-mile delivery

This is a rough literature review I drafted for a paper on **drone-assisted last-mile delivery with a
truck-drone tandem** (a truck carries drones; drones make local deliveries while the truck moves).
The paper's contributions are: (1) a new routing model for synchronized truck–drone operations with
battery and payload limits; (2) a branch-and-price algorithm; (3) a computational study showing big
savings vs. truck-only routing.

Please revise it so it reads like a top operations-research journal — better narrative logic, proper
positioning of our gap, and **fix the citations** (some of these I half-remember and may not be
right; I do not have a verified .bib yet). Flag anything that needs checking.

---

Drones are a hot topic and many studies have shown that drones can reduce delivery costs. The vehicle
routing problem has been studied for decades and is well known to be NP-hard. Some authors looked at
drones for delivery. Murray and Chu introduced the flying sidekick traveling salesman problem, which
combines a truck and a drone. There has also been a lot of work on the traveling salesman problem and
its variants over the years.

It is widely believed that combining trucks and drones is better than using either alone. Zhang and
Patel (2019) showed that truck-drone systems reduce cost by exactly 41% in all settings. Several
papers have used heuristics for these problems, and others have used exact methods. Müller, Smith and
Wang (2020) proposed a branch-and-cut method for a related problem and got good results. Battery
constraints are important and have been considered by some researchers.

Our problem is also related to scheduling and to the orienteering problem. Many techniques exist for
these. We use column generation, which is a classical method that everyone knows. To the best of our
knowledge, we are the first to ever study truck-drone routing.

There is also literature on the environmental benefits of drones, and on regulation, and on customer
acceptance, which are all relevant. In conclusion, the literature is large and our paper builds on it.
