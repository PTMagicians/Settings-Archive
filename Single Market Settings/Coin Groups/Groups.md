You can use PTM to designate GROUPS of coins that have different buy and sell strategies.  For example, you might have a list of coins that are more volatile, so you want to take advantage of this with larger profit settings and stoploss.  You might have another group of coins that you don't want PT to trade unless they meet very specific conditions, or you might have a group of coins which you want to aply different DCA settings. 

The trigger is designed to be true for ANY coin you add to the "AllowedMarkets" field -- any allowed coin that is under 50000% for the day. You MUST NOT leave "AllowedMarkets" blank, or the SMS will be applied to all coins on the market. If you have no coins you wish to hold, use a string that doesn't represent any particular coin (like xxx).

Unlike Profit Trailer, PTMagic doesn't know what market you are trading in, so you must always specify your base currency when using "AllowedMarkets" or "IgnoredMarkets". See the wiki for more information.

**This should be added to the top of your SMS settings, above any other SMS settings that have "StopProcessWhenTriggered": true**


````
	//---------------------
	//   Group 1
	//---------------------
	{
	"SettingName": "Group 1",
	"TriggerConnection": "OR",
	"StopProcessWhenTriggered": false,
	"AllowedMarkets": "xxxBTC, xxxBTC, xxxBTC, xxxBTC",
	"Triggers": [
		{
		"MarketTrendName": "1h",
		"MarketTrendRelation": "Absolute",
		"MaxChange": 500.0
		}
		],
	"PairsProperties": {
		// Your custom settings for this group.
	},
	"DCAProperties": {
                // Your custom settings for this group.
        }
	},
  
        //---------------------
	//   Group 2
	//---------------------
	{
	"SettingName": "Group 2",
	"TriggerConnection": "OR",
	"StopProcessWhenTriggered": false,
	"AllowedMarkets": "xxxBTC, xxxBTC, xxxBTC, xxxBTC",
	"Triggers": [
		{
		"MarketTrendName": "1h",
		"MarketTrendRelation": "Absolute",
		"MaxChange": 500.0
		}
		],
	"PairsProperties": {
		// Your custom settings for this group.
	},
	"DCAProperties": {
               // Your custom settings for this group.
        }
	},
  ````
