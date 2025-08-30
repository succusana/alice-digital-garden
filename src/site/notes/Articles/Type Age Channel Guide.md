---
{"dg-publish":true,"permalink":"/articles/type-age-channel-guide/","created":"2025-08-30T18:08:34.405+01:00","updated":"2025-08-30T18:09:49.709+01:00"}
---

A friend asked me if I could write a guide for a basic age verification channel. In case it's ever useful for anyone else, I'm sharing it here too:

---

If you wish to make a channel where users verify by typing their age, a few steps are necessary:
## Preparation

First, you'll need the bot we'll use for the verification channel, which will be [YAGPDB](https://www.yagpdb.xyz). I would also recommend using a bot to add an embedded message to tell users what to do: [Dyno](https://www.dyno.gg) can do this with its Message Embedder module.

Now for preparing the server itself. Create a channel for the server, and create a role to give users that have correctly typed their age. Notably, make sure that this role does *not* have permission to view the channel you have made, so that verified users don't have the verification channel clogging their channel list.

![Screenshot_20250830_172209.jpg](/img/user/99_Meta/Attachments/TypeAgeGuide/Screenshot_20250830_172209.jpg)

## YAGPDB Setup

We now need to go to YAGPDB's control panel, select your server and then select Advanced Automoderator. We need to create two things here: A ruleset to define what we want the bot to do, and a list.

First, create a list that will contain the ages we want to allow (we will add every age from 18 to 100). Your list should look something like this:

![Screenshot_20250830_172916_Vivaldi.jpg](/img/user/99_Meta/Attachments/TypeAgeGuide/Screenshot_20250830_172916_Vivaldi.jpg)

Now, create the ruleset and give it an appropriate name like Age Verification. Once you have made it, you want to add a Scoped Condition, which will tell YAGPDB when we want it to check for our allowed ages. Set the Type to Active In Channels, and the Options to your channel of choice. I would also recommend adding an extra condition, with the Ignore Roles Type and all of your server's moderator/admin roles in the Options.

![Screenshot_20250830_173102_Vivaldi.jpg](/img/user/99_Meta/Attachments/TypeAgeGuide/Screenshot_20250830_173102_Vivaldi.jpg)

Now for the rule itself. Create a new rule in your ruleset, which then shows Triggers, Conditions and Effects.

Here, we want to add a Word Denylist trigger, and set the effect to Give Role. Make sure to select your role here, and set the duration to 0 so the user keeps it permanently. You should also add a second effect that deletes the user's message, to keep the channel clean.

![Screenshot_20250830_174255_Vivaldi.jpg](/img/user/99_Meta/Attachments/TypeAgeGuide/Screenshot_20250830_174255_Vivaldi.jpg)

YAGPDB is now ready to process typed ages! Remember that your users need to type their age specifically, not their date of birth. 

## Extra Preparation 

As mentioned before, you can add a message embed in the channel using Dyno to instruct users. Go to your Dyno dashboard, select your server and then enable and select the Message Embedder module. Then, create a new embed, name it, set the channel to your verification channel and fill in the details you want. Most notably, you'll want to select a colour, then add a title, description and potentially an image. Then, just press Save, then Save and Send, and you're done! Your channel should look something like this now: ![Screenshot_20250830_174828.jpg](/img/user/99_Meta/Attachments/TypeAgeGuide/Screenshot_20250830_174828.jpg)

## Optional

### Tell users that they have typed incorrectly:

To do this, create a second List like our Allowed Ages list earlier, containing numbers from 0 to 17; This will be our list of disallowed ages. Then, create a second rule under our age verification ruleset, and set the condition to Word Allowlist, add the Allowed Ages list as the option, and repeat this for the Disallowed Ages list. Set the Effect to Send Message, then add a message as you wish.  Make sure to set the message to automatically delete itself after a few seconds.
![Screenshot_20250830_175534_Vivaldi.jpg](/img/user/99_Meta/Attachments/TypeAgeGuide/Screenshot_20250830_175534_Vivaldi.jpg)

### Automatically Ban Users That Report As Under 18:

> [!danger]- Risks of Automatically Banning Users
> Be cautious when using automod rules to autoban users! A typo can easily ban someone and prevent them from ever returning to the server. Ideally, these cases should be dealt with manually or use a kick to allow for staff intervention.
> 

To do this, create the Disallowed Ages list as mentioned above, then create a new rule in the Age Verification ruleset. Set the Trigger to Word Denylist with the Option set to your list of ages under 18, then set the effect to Ban User. Setting a custom message here to inform the user of why they have been banned is optional, but recommended.

![Screenshot_20250830_180455_Vivaldi.jpg](/img/user/99_Meta/Attachments/TypeAgeGuide/Screenshot_20250830_180455_Vivaldi.jpg)