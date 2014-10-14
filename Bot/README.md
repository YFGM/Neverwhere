# Neverwhere Bot README

# IGNORE THIS FILE, WIP

## Installation

*The Neverwhere bot is currently experimental and as such is not deemed ready for release. Full installation instructions will be here when it is deemed stable for release.*

### Requirements 
* Python 3 https://www.python.org/
* gspread https://github.com/burnash/gspread
* pytz http://pytz.sourceforge.net/


## Commands

#Player/Character Registration

**!reg [Player Name] [Password]**

Create new User ID with associated PW, if user does not already exist. 

**!create [Character Name] [Character Sex] [Player Name or ID] [Password] [Str] [Dex] [Int] [Vit]**

Create new character with name and associate ID to User.

**!del [Character Name] [Password]**

Mark character as deleted, data only removed on admin confirm


## Character Creation and Grooming Tools

**!recalc [Character Name or ID]**

Recalculates stats based on attributes and perks, is run periodically and after each command.

**!addP(erk) [Perk Name or ID] [Character Name or ID] [Password]**

Searches for appropriate perk, checks requirements on character. If met, adds perk to the list and runs recalc.

**!removeP(erk) [Perk Name or ID] [Character Name or ID]**

Admin only. Removes a perk from the character and runs recalc.

**!resetP(erk) [Character Name or ID]**

Admin only. Removes all perks from a character and runs recalc.

**!addI(tem) [Character Name or ID] [Item Name]**

Adds the listed item to the characters inventory, seperated by a ','. Only utility, can be done manually.

**!show [Character Name or ID] [Perks] [Inventory]**

Runs recalc and then displays character stat block (also shows bonus text), by default without perks or inventory.

**!addM(oney) [Character Name or ID] [Password] [Amount] [Reason]**

Adds an X amount of money to the character's wealth. Use is logged, abuse at own risk.

**!remM(oney) [Character Name or ID] [Password] [Amount] [Reason]**

Removes X amount of money from character's wealth. Use is logged.

**!sendM(oney) [Character Name or ID] [Password] [Amount] [Receiver Name or ID] [Reason]**

Sends X amount of money from character A to character B. Use is logged.


## Crafting

**!craft [Character Name or ID] [Password] [Item Name] [Skill name or ID] [Value] [Difficulty] [Tool Quality] [Blueprint Quality] [Part Time]**

Add a crafting operation to the character, which is immediately begun full time by default. Displays work that will be done this week, schedules sooner quit if possible. This assumes appropriate raw materials have already been acquired. Once finished, item is put into gathering inventory and message queued. Crafting halts job work.

**!cancelcraft [Craft ID] [Password]**

Cancels a crafting task, gives back the character the appropriate half finished item and resources.

**!showcraft [Character Name or ID]**

Shows what a character is currently crafting and how far they are into the job. Can be looked up in doc.


## Job

**!job [Character Name or ID] [Password] [Type] [Job Site ID] [Part/Full Time] [Salary]**

Registers the character to that job starting the next day. Quits any previous job but does not halt crafting. Jobs recognized: Farming, Farming (Unskilled), Fishing, Lumber (unskilled), Herbalism, Foraging, Herbalism+Foraging, Herb Gardening, Construction (unskilled), Construction (Woodwork), Construction (Stonework), Mining (Overseer), Mining (Unskilled), Smelter (unskilled), Smelter (Foreman). Other jobs are assumed to be RPd out. If you get a salary, it is added from the Job Site foreman's inventory at the end of each week, part time halves the pay.

**!remjob [Job ID] [Password]**

Deregisters any job.

**!showjob [Character Name or ID]**

Fetches character's job, workplace, etc.


## Recovery

**!HP [Character Name or ID]**

Shows character's current HP.

**!FP [Character Name or ID]**

Shows character's current FP.

**!recovery [Character Name or ID]**

Checks if character is in Long or Intensive care. If yes, it shows by who and where.

**!aid [Giver Name or ID] [Password] [Receiver Name or ID] [type] [location]**

Registers giver into giving the other person aid of the appropriate type. If a location is specified, it's resources are used. Expires and returns user to normal job if not accepted within 1 hour. Use !remjob to stop.

*!acceptaid [Acceptor Name or ID] [Password] [Giver Name or ID]*

Accepts an offer for aid and changes job to aid receiver. Quit with !job, !rejob or whenever your giver decides otherwise. Recalc checks if both are still giving aid, otherwise deregisters.

To do: Diseases, poisons, etc


## Consumption 

**!requirements**

Shows the town's current food requirements.

**!setrations [Amount]**

Set the town's rations. Admin only.

TODO: Adding rations, calculating starvation, change ration size


## Worksites

**!newworksite [Name] [Type] [Capacity] etc**

JOBS AND WORKSITES NEED INDIVIDUAL ALGORITHMS. TODO


## Storage

**!store [Character Name or ID] [Password] [Type of stuff] [amount] [Storage Name or ID]**

Stores an appropriate amount of stuff into a storehouse. Use is logged, since abusable.

**!retrieve [Character Name or ID] [Password] [Type of Stuff] [amount] [Storage Name or ID]**

Retrieves an appropriate amount of stored stuff and adds it to your gathering inventory. Use is logged, maybe admin only.


## Utility

**!m(essages) [Player name or ID] [Password] [ID]**

Shows messages the bot has saved for you, also includes automatic messages like reports on crafting and trading. Specifiying an ID opens that message.

**!send [Sender name or ID] [Password] [Recipient Name or ID] [Message]**

Sends a message to that user that is stored until he reads it.

**!op, !deop, !voice, !devoice, !newchannel, !ban, !unban, !roll**

## Trading
TODO
