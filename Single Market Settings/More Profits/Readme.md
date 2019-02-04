## More Profits
by Hojou

This is a simple SMS for PTMagic which will allow you to designate coins you wish to sell for higher profits.  You can also adjust your initial cost settings if you want to buy more of these coins when PT makes it's initial buy.

Some of these settings here need to be adjusted to work correctly with the settings in your PAIRS file.

The trigger is designed to be true for ANY coin you add to the **"AllowedMarkets"** field -- any allowed coin that is under 50000% for the day.  You **MUST NOT** leave "AllowedMarkets" blank, or the SMS will be applied to all coins on the market.  If you have no coins you wish to hold, use a string that doesn't represent any particular coin (like xxx).

Unlike Profit Trailer, PTMagic doesn't know what market you are trading in, so you must always specify your base currency when using "AllowedMarkets" or "IgnoredMarkets".  [See the wiki](https://github.com/PTMagicians/PTMagic/wiki/settings.analyzer#allowedmarkets) for more information.

This should be added to the top of your SMS settings, above any other SMS settings that have "StopProcessWhenTriggered": true 

````
   //---------------------
   //   MORE PROFIT
   //---------------------
   {
     "SettingName": "MoreProfit",
     "TriggerConnection": "OR",
     "StopProcessWhenTriggered": true,
     "AllowedMarkets": "xxxBTC",
     "Triggers": [
     {
          "MarketTrendName": "1h",
          "MarketTrendRelation": "Absolute",
          "MaxChange": 500.0
     }
     ],
     "PairsProperties": {
          "DEFAULT_initial_cost_percentage_OFFSETPERCENT": 200, // requires changes to match your PAIRS setting
         
          "DEFAULT_A_sell_value_OFFSETPERCENT": 300, // you must change the letter A to match your EMAGAIN setting 
          "DEFAULT_trailing_profit_OFFSETPERCENT": 200, // adjust this to suit your settings
     },
     "DCAProperties": {
          "DEFAULT_DCA_A_sell_value_OFFSETPERCENT": 300,  // you must change the letter A to match your EMAGAIN setting 
          "DEFAULT_DCA_trailing_profit_OFFSETPERCENT": 200, // adjust this to suit your settings
     },
   },
  ````   
