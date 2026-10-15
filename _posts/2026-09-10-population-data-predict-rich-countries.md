---
title: "Can Population Data Predict Which Countries Are Rich?"
date: 2026-09-10
layout: post
---

![Feature importance chart]({{ site.baseurl }}/images/feature_importance.png)

Every year, the World Bank publishes GDP and population figures for nearly 200 countries. I wanted to know: if you strip away GDP itself and only look at a country's population size and how fast its population and economy are growing, can you still predict whether it belongs to the world's top 25% of economies? And just as importantly does that prediction hold up fairly across every region of the world, or does it quietly favor some parts of the world over others?

My questions
Do population size and growth trends carry a real signal about a country's economic tier, even without looking at GDP directly?
When the model gets it wrong, does it get it wrong evenly across continents or are some regions more likely to be overlooked?
What I found

Using 24 years of World Bank data (2000 - 2023) across roughly 200 countries, I trained a model to flag "top-tier" economies the top quartile globally by GDP per capita each year using only population, growth rates, continent, and year as inputs.

The model was surprisingly good overall: it identified top-tier economies correctly about 92% of the time, and when it did flag a country as top-tier, it was right 93% of the time.

But breaking that down by region told a different story. The model correctly caught Europe's wealthy countries 94% of the time. Compare that to Oceania, where it missed genuinely top-tier economies 81% of the time, and Asia, where it missed them roughly half the time.

Region	How often the model missed a truly top-tier economy
Europe	6%
North America	33%
Asia	49%
Oceania	81%

Digging into why, continent turned out to be the single most-used signal in the whole model more influential than population or growth rate. In other words, the model had essentially learned a shortcut: "if it's in Europe, it's probably rich." That shortcut works well for Europe, but it means a wealthy country anywhere else has to work much harder to get recognized by the same model.

Why this matters

A 92% accuracy number sounds like a success story on its own. But it can hide a model that's really just leaning on geography as a stereotype rather than learning the economics underneath it. Any time a model like this gets used to screen or rank countries, it's worth asking not just "how accurate is it overall?" but "accurate for whom?"

I'm still turning over one open question: would adding a single extra indicator — say, urban population share, or trade openness — close this gap, or would the model just find a new way to lean on geography?
