---
layout: post
date: 2022-05-27 07:59:00-0400
title: Carbon cost of computing on ARCHER2
description: Are hybrid functionals or flying to conferences worse for the climate crisis?
tags: carbon computing ARCHER2
comments: false
---

With the new [ARCHER2](https://www.archer2.ac.uk/) national high performance
computing facility in the UK, I thought it was time to update my old
<https://jarvist.github.io/post/2017-06-18-carbon-cost-of-high-performance-computing/>
estimate of carbon cost. 

ARCHER2 doesn't seem to state it's power consumption anywhere, but a smaller
[128'000 core CRAY EX based on the same architecture is listed on the Top500
as 637.95 kW](https://www.top500.org/system/179900/). This makes ARCHER2
about 3.7 MW for its 750'080 cores. Perhaps this is why it isn't recorded
anywhere - that is a pretty power hungry beast! (ARCHER was 1.2 MW by
comparison.) Though this is quite a modest 5 W per EPYC core, or 640 W per
compute node. Both these figures seem sensible. 

The new ComputeUnit (CU) metric for job costing is simply a node hour. So one
CU is 0.64 kWh of electricity, or enough to make 25 cups (250 ml) of Tea. 

Our 6 month time allocation as a relatively junior computational group (via
the MCC consortium) was 5000 CU, which consumed 3.2 MWh of electricity.
(Another way to think of our allocation is that it's almost exactly 1 node for
the full 6 months, a 1/5860 share of the whole machine!) 
The UK carbon intensity has been falling (thanks to all those new renewables),
but is still around 0.233 kg of CO2e per kWh of electricity. 
So our compute time was responsible for about 750 kg of CO2e emissions, roughly
equivalent to a round trip flight to Boston to present the data at the Fall MRS
conference. 

I need to patch the `checkScript` command with the extra 1 CU = 0.15 kg CO2e
metric!

Any improved estimates or corrections gratefully received; this blog post is
very much back of the envelope. 

Jarvist Moore Frost

