A simple SMS setting you can use to set a specific price target.  **This can be combined with other custom SMS settings.**

To find the percentage, you can use TradingView to find the percentage gain between your entry and target price.  I recommend setting it a bit below your actual target, to give PT a small buffer to account for your trailing stop, and volatility around resistance levels.


The trigger is designed to be true for ANY coin you add to the **"AllowedMarkets"** field -- any allowed coin that is under 50000% for the day.  You **MUST NOT** leave "AllowedMarkets" blank, or the SMS will be applied to all coins on the market.  If you have no coins you wish to hold, use a string that doesn't represent any particular coin (like xxx).

Unlike Profit Trailer, PTMagic doesn't know what market you are trading in, so you must always specify your base currency when using "AllowedMarkets" or "IgnoredMarkets".  [See the wiki](https://github.com/PTMagicians/PTMagic/wiki/settings.analyzer#allowedmarkets) for more information.

**This should be added to the top of your SMS settings, above any other SMS settings that have "StopProcessWhenTriggered": true**

````
        //---------------------
	//   Target			
	//---------------------
	{
        "SettingName": "Target",
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
		"DEFAULT_take_profit_safety_arm": 9999, // Disable TakeProfit Safety
		"DEFAULT_take_profit_safety_fire": 9998, // Disable TakeProfit Safety
		"DEFAULT_take_profit_percentage": 9999, // Disable TakeProfit Wait
		"DEFAULT_trailing_stop_loss_trigger_arm": 9999, // Disable Trailing Stop
		"DEFAULT_trailing_stop_loss_trigger": 9998, // Disable Trailing Stop
		//
		"DEFAULT_A_sell_value": 7, // This is your target percentage. (Change "A" to match your EMAGAIN strategy)
		"DEFAULT_trailing_profit": 1.5, //  Adjust to suit your needs
		"DEFAULT_trailing_profit_type": "DEFAULT"
	},
        "DCAProperties": {}
        },
````
