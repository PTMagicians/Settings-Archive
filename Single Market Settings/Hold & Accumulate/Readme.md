## Hold & Accumulate
by Hojou

This is a simple SMS for PTMagic which will allow you to designate coins you intend to hold, while still accumulating according to your DCA settings.  Optionally, you can turn off DCA to just hold without any accumulation.

The trigger is designed to be true for ANY coin you add to the **"AllowedMarkets"** field -- any allowed coin that is under 50000% for the day.  You **MUST NOT** leave "AllowedMarkets" blank, or the SMS will be applied to all coins on the market.  If you have no coins you wish to hold, use a string that doesn't represent any particular coin (like xxx).

Unlike Profit Trailer, PTMagic doesn't know what market you are trading in, so you must always specify your base currency when using "AllowedMarkets" or "IgnoredMarkets".  [See the wiki](https://github.com/PTMagicians/PTMagic/wiki/settings.analyzer#allowedmarkets) for more information.

This should be added to the top of your SMS settings, above any other SMS settings that have "StopProcessWhenTriggered": true 


````
      //---------------------
      //   HOLD & ACCUMULATE
      //---------------------
      {
        "SettingName": "Hold",
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
                "DEFAULT_A_sell_value": 50000, // you must change the letter A to match your EMAGAIN setting
                "DEFAULT_take_profit_wait_time_OFFSETPERCENT": 10000,  // to over-ride any take profit settings
                "DEFAULT_take_profit_reset_percentage_move": 0.001
                "DEFAULT_DCA_enabled": "true",  //  "false" if you don't want to accumulate more of these coins
        },
        "DCAProperties": {
                "DEFAULT_DCA_A_sell_value": 50000, // you must change the letter A to match your EMAGAIN setting
                "DEFAULT_DCA_take_profit_wait_time_OFFSETPERCENT": 10000,
                "DEFAULT_DCA_take_profit_reset_percentage_move": 0.001
        }
      },
````
