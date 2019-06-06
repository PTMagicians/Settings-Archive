A simple SMS setting you can use to set a coin-specific stoploss. **This can be combined with other SMS settings to other custom SMS settings.**

The trigger is designed to be true for ANY coin you add to the "AllowedMarkets" field -- any allowed coin that is under 50000% for the day. You MUST NOT leave "AllowedMarkets" blank, or the SMS will be applied to all coins on the market. If you have no coins you wish to hold, use a string that doesn't represent any particular coin (like xxx).

Unlike Profit Trailer, PTMagic doesn't know what market you are trading in, so you must always specify your base currency when using "AllowedMarkets" or "IgnoredMarkets". See the wiki for more information.

**This should be added to the top of your SMS settings, above any other SMS settings that have "StopProcessWhenTriggered": true**


    //---------------------
	  //   STOPLOSS 1 (PT Sell)	
	  //---------------------
	  {
        "SettingName": "Stoploss1",
        "TriggerConnection": "OR",
        "StopProcessWhenTriggered": false,
        "AllowedMarkets": "xxxBTC",
        "Triggers": [
        {
            "MarketTrendName": "1h",
            "MarketTrendRelation": "Absolute",
            "MaxChange": 500.0
        }
        ],
        "PairsProperties": {
            "DEFAULT_DCA_enabled": "false", // Disable DCA
            "DEFAULT_take_profit_safety_fire": 9998, // Disable Take Profit Safety
            "DEFAULT_trailing_stop_loss_trigger_arm": 9999, // Disable Trailing Stop
            "DEFAULT_trailing_stop_loss_trigger": 9998, // Disable Trailing Stop
            //
            "DEFAULT_stop_loss_trigger": -2, // Adjust to suit your needs.
        },
        "DCAProperties": {}
      },
