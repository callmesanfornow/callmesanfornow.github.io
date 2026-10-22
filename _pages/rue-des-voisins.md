---
permalink: /projects/rue-des-voisins/
title: "Rue des Voisins: street-level energy agents"
excerpt: "One street, one transformer, an AI agent in every home."
author_profile: true
---

*Work in progress for the Hi!ckathon 2026 (Hi! PARIS). All results below are simulated, not metered.*

**One street. One transformer. An agent in every home.**

French households already receive national signals that say when electricity is expensive: Tempo red days and off-peak hours. Smart homes react to them. The catch is that when every home reacts to the *same* signal at the *same* moment (every water tank and car charger switching on as off-peak begins), the local transformer that feeds the street can overload.

Rue des Voisins gives each home its own planning agent that saves money for that household, and adds a **station agent** for the transformer. The station only steps in when the sum of all plans would go over the limit.

![Transformer load on a cold red day: off-peak timers versus agents with a station](/images/rue-des-voisins/red-day.svg)

## How it works

Every evening at 18:00, using only what is known at that time (prices, the Tempo colour, the weather forecast):

1. **Plan.** For each home, an optimiser (a small mixed-integer program) chooses when to heat, charge the car, heat water and run the washing machine. It picks the cheapest plan that keeps every comfort rule.
2. **Check.** The station adds up all the plans and compares them with the transformer limit.
3. **Nudge.** If the street would overload, the homes that contribute most get a small local price signal and re-plan. A change is kept only if the street as a whole gets better.
4. **Explain.** A language model reads each resident's wishes in plain words ("I leave at half past eight, I need the battery about four fifths full"). It turns them into settings and explains the plan back in one sentence. Deterministic checkers reject anything invalid and block any change the resident ruled out.

## What we found so far

We backtested the system on the winter of 2024–25, using public French data. The street is modelled on real buildings (222 homes and shops, built from the national building database), but the households are synthetic.

- **Smart homes acting alone make the street worse.** Over the winter, homes optimising only for themselves pushed the transformer over its limit by 2,764 kVAh, against 1,080 kVAh with simple off-peak timers. They all chose the same cheap hours.
- **The station fixes most of it.** With the station agent the overload drops to 624 kVAh: 77 % less than smart homes alone and 42 % less than timers. Nobody's comfort was broken, and the whole street paid €38 more over the winter.
- **Each electric-heated home on Tempo still saves €293 a year** compared with an off-peak timer (median over household variants; range €223–363).
- **Small open language models are good enough to read residents' notes.** They read 98.5 % of settings correctly. When a model agreed to a change a resident had forbidden, the checkers blocked it every time (17 of 17).
- **Electrification raises the stakes.** With half the homes driving an electric car, the cost of coordinating falls on about half the street, up to €81 per home. That calls for a fair way to share it.

## Honest limits

The savings come from a simulation on real data, not from real bills. The transformer's actual size, and which large loads share it, are known only to the network operator. With the assumed values, today's street only overloads if a large shop shares the same transformer. All agent results so far use small open models running locally.

## Data

All public: building data (BDNB), Enedis load curves and per-address consumption, RTE eCO2mix and the Tempo calendar, ENTSO-E day-ahead prices, archived weather forecasts (Open-Meteo) and PVGIS solar data.

*Rue des Voisins is a fictional name for a real street; no real addresses or households are used.*
