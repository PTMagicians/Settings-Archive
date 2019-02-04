## PT DEFENDER
by Hojou

This is a simple SMS for PTMagic which will allow you to create custom settings for coins you are defending with [PTDefender](https://www.ptdefender.com/).  

You should add any additional lines to the Pairs and DCA properties sections of this SMS to customize what PTMagic writes to your pairs and dca settings for coins you are defending.  See the [PTMagic Wiki](https://github.com/PTMagicians/PTMagic/wiki/settings.analyzer) for more information.

The trigger is designed to be true for ANY coin you add to the **"AllowedMarkets"** field -- any allowed coin that is under 50000% for the day.  You **MUST NOT** leave "AllowedMarkets" blank, or the SMS will be applied to all coins on the market.  If you have no coins you wish to defend, use a string that doesn't represent any particular coin (like xxx).

Unlike Profit Trailer, PTMagic doesn't know what market you are trading in, so you must always specify your base currency when using "AllowedMarkets" or "IgnoredMarkets".  [See the wiki](https://github.com/PTMagicians/PTMagic/wiki/settings.analyzer#allowedmarkets) for more information.

This should be added to the top of your SMS settings, above any other SMS settings that have "StopProcessWhenTriggered": true 


````
   //---------------------
   //   PT DEFENDER
   //--------------------- 
   {
     "SettingName": "Defender",
     "TriggerConnection": "OR",
     "StopProcessWhenTriggered": true,
     "AllowedMarkets": "xxxBTC", 
     "Triggers": [
     {
          "MarketTrendName": "24h",
          "MarketTrendRelation": "Absolute",
          "MaxChange": 50000.0
     }
     ],
     "PairsProperties": {
          "DEFAULT_A_sell_value_OFFSETPERCENT": -25, // you must change the letter A to match your EMAGAIN setting
          
          "DEFAULT_trailing_profit_OFFSETPERCENT": -25,
     },
     "DCAProperties": {
          "DEFAULT_DCA_buy_min_change_percentage_OFFSETPERCENT": -15, // adjust this to allow for DCA on coins with a lower 24hr change
          
          "DEFAULT_DCA_A_sell_value_OFFSETPERCENT": -25, // you must change the letter A to match your EMAGAIN setting
          "DEFAULT_DCA_trailing_profit_OFFSETPERCENT": -25,
     }
   },
````
