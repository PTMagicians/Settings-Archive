When trying to fine-tune and analyze my settings, I got tired of searching through PTM's global and sms logs to figure out what settings were active when a particular pair was bought or sold.

So I came up with a nice trick to always see which PTM settings were active in the Profit Trailer Buy and Sell logs.

For example:
![Imgur](https://i.imgur.com/GHoJxBL.png)

With only a few added lines, your PTM analyzer can add a label to each coin throughout PT.  And you can easily toggle it off and on.

The trick is to add a buy/sell strategy that will ALWAYS be true, and then change the labels using PTM.

***

### 1) Stop PTMagic
You should stop PTM while you alter these files, to avoid any errors in PT.

### 2) Edit your PAIRS and DCA files
Go to your **_presets folder in PTM,** and add the following lines to your **PAIRS** and **DCA** files:

PAIRS.properties

![img](https://i.imgur.com/msBkXd1.png)

DCA.properties

![img](https://i.imgur.com/KJGN0pY.png)

You could use **any strategy** you like, as long as it’s something you can ensure is **always true**.  I used RSI because it's easy to work with.   Notice the BUY the value is 100, and for SELL the value is 0, so they will always be true for any possible coin.

### 3) Edit your INDICATORS file  
Go to your **_presets folder in PTM** and add the following lines to your **INDICATORS** file.  Create one labe for **Each GLOBAL and SINGLE MARKET SETTING you use in PTM**.

![img](https://i.imgur.com/y1wsPn1.png)
![img](https://i.imgur.com/IC6uFYA.png)

They don’t have to match the actual names of your PTM settings – they are just the labels you will see on the PT and PTM monitors.  

Don’t forget to add the N/A label you used in your PAIRS and DCA settings.

### 4) Edit your settings.analyzer.json file 
Add the same labels to your PTM settings.analyzer.json file, for the appropriate GLOBAL and SMS settings.  You need to add them to both the PairsProperties AND DCAProperties sections.  This is how PTM will change the strategy labels depending on the active global and single market settings.

![img](https://i.imgur.com/mIaTHJP.png)
![img](https://i.imgur.com/4LWUDm3.png)

![img](https://i.imgur.com/vpdkXJu.png)
![img](https://i.imgur.com/CkOjXtI.png)

### 5) Restart PTM.  
After PTMagic has completed a run, you should see a label for every pair telling you the active global and single market setting.  These labels will show throughout PT and PTM.

If you’ve done everything correctly they will always be true, so it **won’t interfere with your regular buy/sell logic and strategies**.  

**You won’t see the labels for previous buys and sells** in you PT logs, since your new “strategies” weren’t active.  But going forward, all entries in the buy and sell logs will include your new labels.  This will make it **easier when analyzing and adjusting your stategies and settings**, to see exactly what settings were active when a coin was bought or sold.

### 6)  Disable all labels
To easily disable these labels, go to your **PAIRS** and **DCA** files in the **_preset folder of PTM**, and change the labeled strategies to **DISABLED**.  

You don't neet to change anything else.  When disabled, PT will not apply the strategies, regardless of the label changes, so they wont' be visible.

![img](https://i.imgur.com/SWolT9H.png)
