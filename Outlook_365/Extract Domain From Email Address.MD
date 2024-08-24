# Hex Breaker Tech - Power Automate DPA Tutorials

## Episode 1: Extracting the Domain from an Email Address

### Description
Break this common low-level Tech Hex with Power Automate Cloud! 

In this episode, learn how to extract the domain from an email address using a simple formula and automate your workflows. We link the email trigger with the 'Get email' action using the Message ID and show you how to extract the domain name efficiently.

Low Code Formula Examples:
- From Outlook Trigger:
  
  replace(split(split(triggerOutputs()?['body/from'],'@')[1], '.')[0], '.', '')
  
- From Get E-mail Action:
  
  replace(split(split(outputs('Get_email_(V2)')?['body/from'],'@')[1], '.')[0], '.', '')
  

### Script
Welcome to Hex Breaker Tech!  
Today, we’re taking on a tech hex that’s sneakier than Loki with a shapeshifting spell—extracting the domain from an email address using Power Automate. No need to call Doctor Strange for this one; we’ve got it covered. Let’s jump right in because, like the Flash, we don’t have time to waste!

We start by setting up a flow that triggers ‘When an email is received’. This is the first step in lifting this hex—kind of like summoning your Patronus, but without all the wand-waving. Sure, you could use other triggers, but we’re keeping this seance short and sweet. No need to go all *Lord of the Rings* on it.

Next, we need to get the full details of this email. To do this, we’ll use the 'Get email' action. This action needs the Message ID from the trigger—think of it as connecting Thor’s hammer to his hand. Without it, we may as well be just a bunch of people standing around, hoping to be worthy.

Now for the key part—extracting the domain. We initialize a string variable and cast our formula-based spell to slice through that email address like Luke’s lightsaber through the Death Star. This formula splits the email address at the '@' symbol, then slices again at the dot, leaving you with the domain name, polished up and ready for action.

To verify it works, we’ll send an email with the extracted domain as the subject line. This is just one way to use the domain—think of it as your Infinity Gauntlet, with endless possibilities, especially when you start playing in the realm of conditional statements. Snap your fingers, and boom—automation magic!

And that’s it—domain extracted, hex broken! If you found this helpful, make sure to like and subscribe to Hex Breaker Tech for more quick and powerful tech tips. Because, in the immortally fake words of fictional Tony Stark, ‘If we can’t protect your workflows, you can be damn sure we’ll automate them!’

---

