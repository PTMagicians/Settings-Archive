#  Archived Settings - PTM Version 1
## Educational Purposes ONLY

These are **OUTDATED** settings from PTMagic v1 -- they designed to work with Profit Trailer v1.

They will not work with PTMagic v2, or Profit Trailer v2 -- however, they can still provide valuable ideas when developing your own PTMagic settings and trading strategies.

---
---

# Profit Trailer Settings: Quick Sales Strategy
Settings for Profit Trailer and PTMagic. This group of "legacy" settings is geared towards a quick rate of sales and purchases with sell values around 1% each. The settings are heavily dependent on PTMagic. [Download the settings here.](https://github.com/stevenshizzleh/pt_quick_sales/releases) **Please note that I do not intend to maintain these settings once PT 2.0 is released.**

# Background and Settings
## Thought Process Behind Settings
1. Reduce risk. I strongly beleive settings are most successful by careful, thoughtful, and deliberate application of settings that mitigrate risk and exposure to poorly behaved coin pairs. I, like many of you, get my knowledge based on seeing consistent results from others. 

2. Skim the top (credit: YouTube "Crypto Face"). This YouTuber has shown consistent results trading ETH pairs. He's also shown that using little capital while aiming to enter and exit pairs as quickly as possible is a safe and effective method to turn a profit.

3. Increase trailing where appropriate. Trailing sell is set based on a preceived likelihood of favorable returns. If I think "this type of situation has great potential for upside", then the trailing sell is higher. With that, the sell value might be lower. The lower sell value is an acceptance of higher return  but also acknowledging that things don't always go the way we want them to.

4. DCA's are good and vary in depth. What I've seen in "bearish or better" markets so far is that when trading 4 pairs at a time (what I'm doing at the moment), no more than one pair will enter a DCA4. From there, my assumption is that two pairs will not go deeper than DCA3 and I'll get lucky with another pair and only hit a DCA2. This is my most likely worst case scenario. Can it be worse? Yes. Can it be better? Sure! So this assumption, plus my current operating limit of 4 pairs, is what leads me to an ALL_max_cost_percentage of 2.75% in my PAIRS.properties page. A DCA might tie up your capital, but it'll also increase your returns with each level of DCA.

## Market Trends
The trends that I have in place are based on necessity. I identified times where I either missed an opportunity, or suffered a loss due to not capturing a change in a specific time period. One of the things I've noticed is that the most important trends are all within 24 hours. It seems 24 hours and 3 days are strong benchmarks for stability of a pair, so I rely on those to determine what kind of risk a pair presents. The name of the game is to mitigate risk and seize opportunities
that either present minimal risk and evidence of growth.

## Global Settings
Bearish settings are based on a 3 hour anchor. This seems to be a good metric for determining overall health of a market. Bullish settings also require an anchor on 1 hour performance. This is because the bullish settings introduce additional risk, so we use an additional metric to ensure the bullish trend is consistent.

## Favorable Single Market Settings

### High Performance
The pair has shown a significant amount of growth in nearly all timescales. The growth of the pair is such that it would not be appropriate to use EMAGAIN since there is such a divergence between the slow and fast EMA lines. In this case, we use the LOWBB strategy and look for a pair to dip to half way between the top and bottom bollinger bands. In other words, the value of the pair falls to meet the SMA between the bands. Low trailing buy value is used due to the high performance of these situations. It's not very likely that a dip would continue for long enough to "trail" it. Highest trailing profit of all settings.

### Dip During 3hr Pump
The pair has been performing well but took a bit of a dip. The strength of the pair suggests it could make a comeback to its previous value. Else, the performance of the pair suggests if it goes into DCA, it won't be for long. Higher railing profit than other settings. Might be getting rid of this, we'll see.

### Recent Downtrend but 12h to 24h Support
The last 1hr of the pair has shown a dip, but 12hr - 3 day shows positive support. This might just be a random dip. There might a DCA or two, but again, positive support shows a recovery from the dip is a possibility. 

### Well Behaved 3h to 12h
The pair has displayed consistent behavior in the midterm. Higher trailing profit than the default setting

## Unvavorable Single Market Settings (least favorable first)

### New Coin
Too much risk. Remove if you want to try to jump on a pump.

### Downtrend
Do not purchase a coin that is showing excessive loss risk in any time period. People have commented that downtrend disables a lot of pairs. This is by design.
Why would I want to invest money in something that has shown nothing but consistently poor results?

### High Risk Pump
These coins are showing very high increases in value. The chance that they will crash is too great to risk. If the coin were purchased and DCA enabled, it would consume a large majority of capital. If a coin that was purchased and in pairs become a high-risk pump, then we're very likely in the green. This setting will take advantage of that fact. It has a huge sell value and trailing profit to ride a coin pair to the peak.

# FAQ
Q: Will this work with BTC?

A: Yes. You will need to update the below properties in your PAIRS.properties.

    market = BTC
    ALL_max_trading_pairs = [your value here, see next question]
    ALL_min_buy_volume = [your value here, recommend 400-700]

Q: What should I set ALL_max_trading_pairs to?

A: You'll need to determine what your max trading pairs is based on your comfort levels, balance, DCA levels, and risk acceptance. Let's say you have a good ETH balance like 2 ETH....in this case I'd trade more pairs, instead of larger pairs. This will pool your risk among many pairs. If you have a lower balance, then clearly you'll only be able to run less pairs. The true limiting factor on the number of pairs you run is your DCA setup. The current DCA setup is "shallow" and I'm currently testing a much greater depth of DCAs. For the time being, recommend you check out [this file](https://docs.google.com/spreadsheets/d/1RAh-xjqsOQITBZmaf2ZTbPqq2aqjyKwF_kJuesaMFPc/edit?usp=sharing) provided by JB, a member of the Crypto Gnome team.

Q: Why do you use ALL_max_cost_percentage instead of ALL_max_cost?

A: Bottom line up front: to make sure you're compounding. Longer explanation: if you use percentage, then each time you buy it will take into account previous gains/losses. If you're making gains, subsequent buys will be larger and will in theory return greater net gains.

Q: Why are so many pairs in Sell Only Mode?

A: This group of settings was designed to get in and out of pairs that show favorable behavior. It avoids anything that can be risky like downtrends and pumps. Unfortunately, a lot of pairs just don't make the cut. If you want to trade pairs that are downtrending, remove the downtrending setting. Another option is to change the ALL_buy_strategy to something like LOWBB or EMAGAIN. I tried this and wasn't pleased with the results because the whole point of these settings is to get IN AND OUT as quickly as possible. If you want look at holding a pair for days at a time, then this setup might not work for you. Or, you'll need to adjust your DCA levels for a much greater level of depth.


Q: What will the sales look like?

A: Like this:

![Sales Log Example](https://imgur.com/MEfz177.jpg)

