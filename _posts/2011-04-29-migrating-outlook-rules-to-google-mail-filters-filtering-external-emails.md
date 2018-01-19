---
layout: post
title: Migrating Outlook Rules to Google Mail Filters – Filtering External Emails
---
Further from my recent post on <a href="https://davidrcook.wordpress.com/2011/03/28/migrating-outlook-rules-to-google-mail-filters/" target="_blank">Google Mail Filters</a>, another rule that I had setup in Outlook was to move emails that originated from outside my organisation into a separate folder &quot;Inbox - External&quot;. This way marketing information, or newsletters for example wouldn't clutter my inbox. There isn’t a predefined scenario in the Outlook Rules Wizard to handle this, but you can achieve the desired result by setting the “with specific words in the sender’s address” to “@” and adding an exception “except with @myorganisationdomain.com in the sender’s address” as shown below. Effectively the rule states that all emails except those originating from my organisation should get moved to the defined folder.

<a href="http://davidrcook.files.wordpress.com/2011/04/image.png"><img style="background-image:none;padding-left:0;padding-right:0;display:inline;padding-top:0;border-width:0;margin:0 0 0 10px;" title="image" border="0" alt="image" src="http://davidrcook.files.wordpress.com/2011/04/image_thumb.png" width="413" height="496" /></a>

You will see in the screenshot that I also have exceptions for specific individuals and domains. What I found was that after setting this rule up, I was missing important emails as they were being moved out of my Inbox. For example, emails from the client of the project I was working on, my car pool buddy (in case he was leaving early that day), and of course my wife. Effectively you can set these up as exceptions to the rule by adding them to “except if from” or “except with @clientdomain.com in the sender’s address”.

Now that we have moved to Google Mail, I wanted to replicate the rule in the Google Filters.
1. Under **Settings** -&gt; **Filters** select **Create a new filter**
2. On the Choose search criteria screen, set:      
- **From**: –@myorganisationdomain.com (note the minus before the @)
- **To**: me 
- **Doesn’t have**: from: wife OR from: car.pool.buddy (obviously replace with the names you want to exclude) 
3. Use the **Test Search** button to test the criteria you have entered. The filter looks something like this: 
![filter1]({{ site.baseurl }}public/images/filter1.png){:height="108px" width="700px"}
4. Click **Next Step &gt;&gt;**
![filter3]({{ site.baseurl }}public/images/filter1.png){:height="172px" width="689px"}
5. In the Choose action screen, tick “Skip the Inbox” and tick “Apply the label: Inbox – External”
6. Click **Update Filter**