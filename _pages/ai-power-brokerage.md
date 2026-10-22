---
permalink: /projects/ai-power-brokerage/
title: "AI Agents as Power Brokers"
excerpt: "Self-interested household AI agents that broker their flexibility with a transformer agent, so a whole street stays within its shared limit."
author_profile: true
redirect_from:
  - /projects/rue-des-voisins/
scholar_title: "AI Agents as Power Brokers: Coordinating Self-Interested Household Energy Agents under a Shared Transformer Limit, Backtested on French Open Data"
scholar_authors:
  - "Sankaran, Aditya Narayan"
scholar_date: "2026/10/22"
scholar_institution: "Télécom SudParis, Institut Polytechnique de Paris"
scholar_pdf: "/files/ai-power-brokerage/sankaran2026powerbrokers.pdf"
---

*A passion project: a product idea and proof of concept. All results are simulated, not metered.*

**[Technical report (PDF)](/files/ai-power-brokerage/sankaran2026powerbrokers.pdf)** · **[Slides](/files/ai-power-brokerage/slides.html)** (use the arrow keys)

## The idea

Every home on a street is fed by the same local transformer. French households already get national price signals (Tempo red days, off-peak hours), and smart homes react to them. When every home reacts to the *same* signal at the *same* moment, the shared transformer overloads.

So I gave each home an AI agent that acts as a **broker** for that household. It knows the household's wishes, plans tomorrow's heating, car charging, hot water and laundry at the lowest cost, and offers its flexibility to the street. A **station agent** speaks for the transformer. It brokers the street's limited capacity and only steps in when the sum of all plans would go over the limit. Homes are not asked to share or sell energy to each other. Each one still acts for itself.

![Transformer load on a cold red day: off-peak timers versus agents with a station](/images/ai-power-brokerage/red-day.svg)

## How the brokerage works

Every evening at 18:00, using only what is known at that time (prices, the Tempo colour, the weather forecast):

1. **Plan.** For each home, an optimiser (a small mixed-integer program) chooses the cheapest plan that keeps every comfort rule.
2. **Check.** The station agent adds up the plans and compares them with the transformer limit.
3. **Negotiate.** If the street would overload, the station asks the homes that contribute most to shift, with a small local price signal. Each house agent accepts or declines according to what its resident allowed. A change is kept only if the street as a whole gets better.
4. **Explain.** A language model turns residents' plain-language notes ("I leave at half past eight, I need the battery about four fifths full") into settings, and explains the plan back. Deterministic checkers block anything invalid or anything a resident ruled out.

## What the proof of concept shows

I backtested the system on the winter of 2024–25 with public French data. The street has 222 homes and shops modelled on real buildings, but the households are synthetic.

- **Smart homes acting alone make the street worse.** Homes optimising only for themselves pushed the transformer over its limit by 2,764 kVAh over the winter, against 1,080 kVAh with simple off-peak timers. They all chose the same cheap hours.
- **Brokering fixes most of it.** With the station agent the overload falls to 624 kVAh: 77 % less than homes acting alone and 42 % less than timers. Nobody's comfort was broken, and the whole street paid €38 more over the winter.
- **Each electric-heated home on Tempo still saves €293 a year** compared with an off-peak timer (median over household variants; range €223–363).
- **Small open language models are good enough as brokers' front desks.** They read 98.5 % of settings correctly from residents' notes. When a model accepted a request that a resident had forbidden, the checkers blocked the change every time (17 of 17).
- **Electrification raises the stakes.** With half the homes driving an electric car, the cost of coordinating falls on about half the street, up to €81 per home. That calls for a fair way to settle it.

## Limits

The savings come from a simulation on real data, not from real bills. The transformer's actual size, and which large loads share it, are known only to the network operator. With the assumed values, today's street only overloads if a large shop shares the same transformer. All agent results so far use small open models running locally.

## Data

All public: building data (BDNB), Enedis load curves and per-address consumption, RTE eCO2mix and the Tempo calendar, ENTSO-E day-ahead prices, archived weather forecasts (Open-Meteo) and PVGIS solar data.

## Cite

> Aditya Narayan Sankaran. *AI Agents as Power Brokers: Coordinating Self-Interested Household Energy Agents under a Shared Transformer Limit, Backtested on French Open Data.* Technical report, Télécom SudParis, 2026.
