---
name: Routing for a bus based evacuation 🚍
tools: [C++, Combinatorial Optimization, GRASP, Operations Research]
image: ../assets/images/bep-grasp/preview2.jpg
description: Scheduling bus routes for an evacuation with Combinatorial Optimization
---

# Scheduling bus routes for an evacuation... with Combinatorial Optimization

Let's imagine a large-scale emergency event it's about to happen. It could be a tsunami, a wildfire, a bomb attack, etc. As an evacuation organizer, you get a notice a while before the emergency strikes. You have at your disposal the city buses to evacuate the residents located inside the risk zone, and take them to available shelters outside the endangered area.

{% include figure.html image="https://assets.metrolatam.com/cl/2015/10/02/desastres-1200x600.jpg" caption="Here are some of the natural catastrophes that took place in 2015 in my country (Chile)... Nice" %}

Buses are, initially, located in depots (also called yards). They must travel to assembly points (a common point where people gather to wait for the buses), pick a group of evacuees, and take them to one of the shelters.

Which assembly point should the bus visit first? And in which shelter is the better to take the evacuees picked on that ride? The closest one may not always be the best decision in terms of the complete picture.

{% include figure.html image="../assets/images/bep-grasp/graph.png" caption="We can represent the scenario as a graph." %}

To simplify, let's imagine the scenario in terms of a graph. Yards, assembly points and shelters are nodes, and they are connected by the available roads. Each assembly point has a demand, and each shelter has a capacity. Each bus has, also, a maximum load capacity.

This problem was described by Douglas R. Bish as the [Bus Evacuation Problem](https://link.springer.com/article/10.1007/s00291-011-0256-1). The scenario was stated as a **mathematical programming formulation**, and the idea is to use combinatorial optimization to find the "best" route for each bus, in order to minimize the total time of the evacuation, which is the evacuation time of the bus that makes the longest route (we'll consider that time and distance are interchangeable concepts).

In this project, I used an algorithm based in **local search** to find a good quality and, hopefully, near-optimal solution for this routing problem, since, off-course, trying to check all the combinations is impossible in this universe at this point. So, what this algorithm does, is to "navigate" the search space in a kinda "smart" way, to find a solution that is much better than a randomly generated one, and, hopefully, near optimal.

You can see the full project source code and read the bachelor's thesis work on the repo. The thesis is in Spanish 😑, but a published article about the full work is available [here](https://ieeexplore.ieee.org/document/7969589).

<p class="text-center">
{% include button.html link="https://github.com/jjloyola/bep-grasp" text="Watch full repo" %}
</p>
