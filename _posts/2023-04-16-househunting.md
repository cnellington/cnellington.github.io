---
layout: post
title:  Hesitation Devastation and a Framework for Making High-value Decisions Without Hating Yourself
date:   2023-04-16 10:00:00
description: House hunting, recruiting, and picking the right fruit at the grocery store
tags: life math statistics
categories: personal
---
### Analysis Paralysis in the Housing Market
For the past week, I've been consumed by the highly involved and coordinated dance of apartment hunting.
When you enter this dance, you're doe-eyed and excited to find your cinderella or prince charming.
You switch partners a few times, testing the waters and considering your options.
Do I prefer the one with central AC or the backyard? Certainly not the one by the train tracks. 
You'll leave some suitors disappointed, stepping on a few toes, but feeling like options are in excess.
Suddenly your own toes are smashed. 
"We've already received several applications for this unit, we'll be in touch if they aren't approved."
They always are.
You look around the dance floor, and realize the cinderellas and prince charmings you danced with are leaving. 
Only Train Tracks remains, and she's been waiting on you all night.

This situation seems common in markets with high demand that also require enormous personal investment.
Shopping in this market is a balancing act: you want to find a great, affordable option,
but you need to lock in an option fast, before it gets scooped up by another buyer.
The size of the investment means most buyers will only rarely visit the market,
requiring them to create a new scale every time they're looking to buy to gauge the quality of their options. 
But excessive demand means this scale is usually based on just a handful of options they've been able to 
consider in their first day on the market.

And so, you've danced the dance for one day. 
One partner was very good, not perfect, but you could see yourself leaving with them.
Are they the best option, and your standards are too high?
Or are they fairly mediocre, and you have yet to see the best options?
You succumb to analysis paralysis, faced with too many potential options to consider and an
investment too big to get wrong.
You decide to sleep on it, waiting another day to see a few more options.
The next morning, the market's invisible hand provides a swift back-hand across the face when the apartment is unlisted.
Your analysis paralysis has subsided, and you are now left with a throbbing case of hesitation devastation.

As you can imagine, figuring out when to invest a huge sum of money in a fast-paced market has implications
outside of just figuring out which student slumlord to rent from.
A more classic version of this problem is directed toward figuring out when to recruit an employee,
but it applies the same to apartment hunting, buying a car, getting pretty much anything off of
craigslist or facebook marketplace, and even to getting groceries on a time crunch.
I'm revisiting this problem for two reasons:
1. It provides me a timely answer about what apartment to lease.
2. My girlfriend must also acknowledge that my job is cool and useful.

### A Probabilistic Approach to Signing Your Lease
To make the right choice with a very limited number of options, you need to figure out
how the options you've seen compare to the rest of the market you haven't seen.
The spirit is being able to commit after determining when you've seen an option that's "good enough" for you.

*Skip ahead to the table if you want to see the framework without the math*

Formally, we'll say every option has a quality $$X$$, where the quality is something you determine based on 
attributes you care about.
For an apartment, the quality might be based on a tradeoff between price, sqft, amenities, and location.
We'll assume that the quality for your market (the options you would consider) is normally distributed,
where most options are average, and much better or much worse options are rarer.

$$ X \sim N(0, \sigma^2) $$

To make a choice, we'd like to know with confidence at least $$1 - \delta$$ when we've seen an option 
with higher quality than $$\epsilon$$ percentage of the market.

$$P(max(X_1, ..., X_n) > Z_{\epsilon}) > 1 - \delta$$

Where $$Z_{\epsilon}$$ is the quality value that is higher than $$\epsilon$$ percent of all $$X$$
(the z-score for our normal distribution),
and we'll choose how many candidate options $$n$$ we should consider before meeting the quality
and confidence criteria.
To get the same answer, as can figure out how likely it is that none of our options meet a quality threshold.

$$P(\bigcup_{i=1}^n [X_i \leq Z_{\epsilon}]) \leq \delta$$

$$\Pi_{i=1}^n P(X_i \leq Z_{\epsilon}) \leq \delta$$

$$\Pi_{i=1}^n \epsilon \leq \delta$$

$$\epsilon^n \leq \delta$$

$$n > log_{\epsilon}(\delta)$$

Where the union factorizes because each observation is independent (one apartment quality doesn't
affect another).


Now we have a nice closed-form answer for how many options we should consider before committing!
If we want to see an apartment of quality better $$\epsilon$$ percent of our housing market with probability  $$1 - \delta$$,
we can use $$n = log_{\epsilon}(\delta)$$ to find the minimum apartments we should tour.
This table has the values for $$n$$ rounded up to the nearest whole number.

|     |                   |                              |                                       |                    |                   $$1 - \delta$$                    |                                       |                                        |
|-----|------------------:|---------------:|:---------:|:---------:|:---------------------------------------------------:|:---------:|:----------:|
|     |                   |  | &nbsp; &nbsp;  $$0.6$$ &nbsp; &nbsp;  | &nbsp; &nbsp;  $$0.7$$ &nbsp; &nbsp;  |        &nbsp; &nbsp;  $$0.8$$ &nbsp; &nbsp;         | &nbsp; &nbsp;  $$0.9$$ &nbsp; &nbsp;  | &nbsp; &nbsp;  $$0.95$$ &nbsp; &nbsp;  |
|     |           $$0.6$$ |                |     2     |     3     |                          4                          |     5     |     6      |
|     |           $$0.7$$ |                |     3     |     4     |                          5                          |     7     |     9      |
|  $$\epsilon$$   |           $$0.8$$ |                |     5     |     6     |                          8                          |    11     |     14     |
|     |           $$0.9$$ |                |     9     |    12     |                         16                          |    22     |     29     |
|     |          $$0.95$$ |                |    18     |    24     |                         32                          |    45     |     59     |

<br>
So if you want to be 90% sure you've toured an apartment better than 70% of the market, the table says for $$1 - \delta = 0.9$$ and $$\epsilon = 0.7$$ you should tour 7 apartments before committing. 
If you want to be 95% sure you've toured an apartment better than 90% of the market, you should tour 45 apartments (not recommended).
Anecdotally, I toured 11 apartments before putting a deposit down and I feel confident that I've seen at least 1-2 in the top 20% of my market.

I'd like to think this is generally helpful for making decisions everywhere, although 
I probably won't be using this to see how many pieces of produce I should squeeze at the market before being confident about my choice, 
unless I need to limit myself to 1-2 MPFS (minutes per fruit selection).