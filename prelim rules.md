## The combat system
The core of the game is forced movement. Attacks cause knockback away from the attacker. Some attacks feature built in gap closers. A sword user might jump and stab down, leaping forward 5ft. A spear user can charge forth, moving forward 20ft and attacking anything in the path, for example. 

The character attributes are BREAK and HP. Despite HP being a resource, BREAK is the real value of life. Your HP, what starts at 100 can reach 0 and you won't die. Your BREAK, what starts at 0 can reach 100 and you will.

The more an attack knocks you around, the more it'll increase your BREAK meter. BREAK passively cools off with each step in a round's timeline. The rate at which BREAK lowers is tied to how high your HP is. If you're healthy, you recover from BREAK easily.

The less an attack knocks you around, the more it'll damage your HP meter. An arrow probably won't send you across the room, but it'll pierce. 

HP is also the spellcasting resource. Some spells only cost actions, others may ask for HP. A mage can cast spells until their HP is at 0 and be fine, as long as they don't get smacked around from this point on.

The point of weapons is to either wound, to deal BREAK damage, or do both.

The point of spellcasting is to provide utility, like corral enemy movements and prevent certain movements. Walls of earth rising from the ground, or encroaching flames. A mage creates stage hazards.

Tokens have facing. And some attacks might perform differently depending on where it's hitting--or where it's coming from. A punch might be more effective if it's face-on, or a knife might be more effective in the back. A swinging attack that cleaves in an arc might throw enemies at your sides further than enemies at your back.

It's harder to hit enemies that are positioned behind other enemies. It's not a chance to miss, more like a chance to body block. If a mage is positioned behind another enemy and you fired an arrow at the mage, the enemy in front is more likely to take the arrow. In this way, its possible to assemble defensive lines.

During a round, each player may use three actions and a reaction. Skills consume a number of actions set by their item sheet. If a player moves their token, the action step on they're selecting on the timeline becomes consumed by a generic movement action. Every 25ft of token movement consumes an extra action.

A reaction can be interjected between actions. For example if a player is going to swing their sword at you on action 1, and you have a reaction skill available like to grab and redirect the swing, you may click reaction first thing and it'll be placed before action 1 on your timeline. When both teams consent to a round end and the timeline executes, the reaction will activate on the targeted enemy and both players will have to roll a dice defined by the reaction skill. 1d20 for example. If the enemy player executing the reaction rolls higher and wins the bout, they successfully redirect the swing and nullify the attack.

Each round operates on a timeline of seven steps. Every player has their own personal timeline. Reactions are placed on odd steps and actions are placed on even steps. Some skills cost more than one action. Which action the skills' effects play out on is up to the skill.

A player has a personal timeline on their battle hud. If a player goes to move their token during a round, movement won't happen immediately. Instead, every step of movement will appear as a ghostly copy of the player token. Which positions are ghostly is whichever ones don't lie on the currently selected step in the timeline.

There is no initiative in this game system. Both teams act at once. During a round, a player fills out their timeline, make their plan, then click ready. The closest scenario to initiative is a surprise attack, in which one team is simply marked as can't act during the first turn.

A round ends when all players mark themselves as ready. During a round end, the GM may progress the timeline in single steps. Every player's personal timeline will play out at the same time. 1-2-3-4-5-6-7. The players will be shown their character actions playing out. Where they end up at the end of round end, they'll start at in next round. Battle continues until it ends.

## Documents
### Item tagging as a design helper
All items are subject to a universal tagging system. Tags are used for all manner of functions. Like the equipment slot on a character sheet will search for tags on an item like "head" to see if it's allowed in the head slot.

- Tags are managed by a centralized tag manager which is accessible through system settings.
- Tags appear as chips on an item sheet
- Tags are set on an item in the rules tab. There are two fields, "tags" and "hidden tags"
- Hidden tags behaves the same as tags, except isn't pushed to display on the item sheet.
- Tags always appear as chip input.
- Right clicking a tag toggles its display between its label and its UUID.
----
### Standard elements
In a lot of sheets, I list the same elements over and over so maybe it'll help to have a list of them? Like so you can just import in with handlebars or whatever. Some tabs like rules are meant to display different things for different item types so I don't know if that method will work, iunno.

- **Description** - A tab with only an editable rich text field.
- **Rules** - At its simplest, has a field displaying the UUID of the item it's in, the hidden tags field, and a field for "short description" which is another description rich text field meant for use in item cards. The rules tab can only be seen by GMs.
- **Effects** - A drag and drop for action-type items. When an item with the effects tab is present and not inert on a character sheet, the character gains the actions listed. Actions within an effects tab displays as item cards. Clicking one of these cards uses the action, if it can be used. Otherwise, it just lints the action in chat.
- **Item Cards** - Truncated previews of an item sheet, meant for linking in chat or display within another sheet. It should display the item's icon, name, and the short description from the rules tab.
- **Price field** - It mostly appears in an item sheet's footer. It would be nice for this to be an import.
- **Inventory** - A tab that simply displays slots.

----
> #### Items
> Physical Items
> - [Material](#material)
> - [Weapon](#weapon)
> - [Tool](#tool)
> - [Storage](#storage)
> - [Consumable](#consumable)
> - [Equipment](#equipment)
> - [Kit](#kit)
> - [Deployable](#deployableitem)
>
> Character Building Items
> - [Action](#action)
> - [Training](#training)

####
----
### Physical item: "Material" <a name="material"></a>
###### description:
*Is an inanimate item type. It will most commonly be used for treasures and baubles.*
###### about its sheet:
- Its item sheet is made of two panels laid out horizontally.
- **Within the left panel**: Is its image, spanning a large section of the sheet.
- Above the image, in like Header4 text is its name.
- Below the image, is its tags field.
- **Within the right panel**: the description and rules tabs. It also has a price field, which exists as a footer only in the right-side panel.
###### a tally of its tabs and imports basically?:
- description
- rules
- price
----
### Physical item: "Equipment" <a name="equipment"></a>
###### description:
*Equipment are items which are inert unless placed in the correct slot in the character sheet. When active, items grant characters active effects.*

*Through active effects, an item can increase a player's stats or subtract a flat number from incoming damage like how armor hardness in pathfinder does or even grant entire actions for a player to use, like a shield granting "raise shield" or a spiked gauntlet adding a spiked punch action for players to use.*

###### about its sheet:
- Equipment is inert until placed in a character's equipment slot. Since the equipment slot itself will handle what can be placed in it, all the item needs to worry about is that it's in an equipment slot at all. 
- Copies the stylings of the material sheet, except:.
- **Within the right-side panel**: is now also an effects tab.
- **Within its rules tab**: A checkbox for "always inert" which hides the contents of the effects tab from players.

###### a tally of its tabs:
- description
- effects
- rules
- price
----
### Physical item: "Weapon" <a name="weapon"></a>
###### description:
*Although functionally equivelant to the equipment item type, the weapon slot on the actor's character sheet is core to the game's identity.*

*Weapons have different qualities, like light or heavy. A quality adjusts the effectiveness of an action belonging to the item in question depending on a character's stats. Like a weapon with the heavy quality will be better for characters with a high weight class*

###### about its sheet:
- Copies the stylings of the material sheet, except:
- **Within the left panel**: The description is now on the left panel, beneath the item image.
- The quality is displayed as something like a chip to the right of the item's name.
- **Within the right panel**: An effects tab and the rules tab.
- Because the rules tab is only visible to GMs, it'd be nice if players didn't see tabs at all here but just the contents of the effects tab. Is that doable? 
- **Within its rules tab**: A checkbox for "always inert" which hides the contents of the effects tab from players.
- A dropdown to select the weapon's quality.

###### a tally of its tabs:
- description
- effects
- rules
- price
----

### Physical item: "Tool" <a name="tool"></a>
###### description:
*Tools are a general purpose for any item which used. A bomb, a trap kit, a magnifying glass.*

*What makes a tool different from an equipment item is that it isn't rendered inert if not in an equipment slot. Although actions from a tool won't be carried over to the player's actions tab. The experience I want to make in gameplay by doing this is that a player will have to dig around their inventory for the tool when they remember they have it, rather than simply perusing their actions list until they find something that fits their situation.*
###### about its sheet:
- Copies the stylings of the material sheet, except:
- **Within the right panel**: An effects tab, which goes alongside the description tab.
- **Within the rules tab**: A checkbox for "always inert" which hides the contents of the effects tab from players.
###### a tally of its tabs:
- description
- effects
- rules 
- price
----

### Physical item: "Storage" <a name="storage"></a>
###### description:
*Storage items grant extra slots in a player's inventory.*  
*Storages are only active if either A. Placed in an equipment slot. B. Placed in the first six slots of the character's inventory.*  
*Hovering your mouse over a slot containing a storage item will highlight the inventory slots granted by that item, to make it easier to tell what's stored where.*

*Some storages can be safely taken off, like backpacks.*    
*Some storages work only when placed in an equipment slot, like a magic ring.*  
*Some storages don't grant inventory slots at all, but must first be placed down on the canvas and opened, like a chest*

*Storages like backpacks have their own inventories, whose slots mirror the slots that it adds to the player's inventory. So it's more like the character inventory links the slots that actually only exist in the backpack's item. When the backpack is removed, the character inventory slots simply stop being linked.*

*Storages like the magic ring have no individually accessible internal inventory. Its character sheet has no visible slots. When the ring is taken off, items stored in its slots drop out of the player's inventory and onto the ground.*

*Storages, like the chest have internal inventory slots but do not add to the character's inventory.*

###### about its sheet:
- Copies the stylings of the material sheet, except:
- The sheet's display changes radically depending on options set in the rules tab.
- **Within the rules tab**: A text field to input the number of slots this storage has.
- A checkbox for: Must be placed in an  equipment slot.
- A checkbox for: Drops stored items when placed on game canvas.
- A checkbox for: Drops stored items when placed in actor inventory.
- A checkbox for: Displays its internal inventory on its own sheet.  
**If displays internal inventory is on**:
- **Within the left panel**: The description is now on the left panel, beneath the item image.
- **Within the right panel**: An inventory tab.   
**If displays internal inventory is off**:
- Copies the stylings of the material sheet exactly, just an image, a name, and a description. Its inventory is still there, just not visible.
###### a tally of its tabs:
- description
- inventory
- rules
- price
----

### Physical item: "Consumable" <a name="consumable"></a>
###### description:
*An item which has charges which tick down on use.*  
*On use, it grants active effects..*
###### about its sheet:
- Copies the stylings of a material sheet except:
- **Within the right side panel**: There's a new internal header with a "Use" button to the left and a charges count to the right.
- Has an effects tab, which is hidden from the player.
- **Within the rules tab**: A checkbox for "refillable." If checked, the item will not disappear when its charge count reaches 0.
- **If the item is on the game canvas**: The use button will be unclickable unless the character token is within 5ft/one grid space of the item's token.
###### a tally of its tabs:
- description
- effects
- rules
- price
----

### Physical item: "Kit" <a name="kit"></a>
###### description:
*A kit is an item which stores other items for immediate use.*  
*The player might be able to rearrange what's in a kit by dragging and dropping, but a player can't add or remove items.*  
*A kit has no maximum number of slots. Therefore, its inventory sheet flexes and displays slots as needed*

*A chef's spice kit might have three consumable items inside: salt, pepper, cajun.*  
*The player would open the kit, whose sheet is largely the three items stored inside in inventory view. They would then click on salt to open its consumable sheet, and click use.*
*The salt shaker item would be set up with an effect that adds a "pinch of salt" item to the player's inventory.*

###### about its sheet:
- Has a very lightweight header with a small image icon and name.
- Below the header is simply the inventory tab.
- Has a price footer.
- has a rules tab

##### a tally of its tabs:
- inventory
- price
- rules
----

### Physical item: "Deployable" <a name="deployableitem"></a>
###### description:
*A deployable is an item which can be placed on the canvas and used in unique ways.*  

*A tent kit will have a button to add a tiles which makes a tent on the canvas.*  
*A turret will immobilize the player and grant them a shoot action.*

*Because deployables are so varied, its sheet and use should be programmable on a per-item basis.*

###### about its sheet:
- There will be two tabs: Sheet and Rules.
- **Within its rules tab**: Three fields: javascript, html, css.
- The volitile sheet that the deployable creates should display to the GM wrapped inside the sheet tab, if this is doable.
- When a player tries to open the deployable, what will open is the volitile sheet.

----

### Character item: "Action"
###### description:
*An action can be configured in several mods: Maneuver, Offensive, Defensive, Passive*  
*Actions are what are dragged into an item's effects tab.*  
*Maneuvers, Offensive, and Defensive actions display in a character's actions tab.*  
*Passive actions display in a character's Active Effects tab.*

> ###### Action: Maneuver
> *Interaction-type actions, like "search around" or "jump."*
> - **Within its rules tab**:
> - A checkbox, for "unavailable in combat"
> - An "Action,Reaction" dropdown, next to a "one,two,three" dropdown. If "reaction" is selected, then "one,two,three" does not display.
> - A checkbox, for "applied to self." If unchecked, a token must be selected for the action to be used.
> - A drop-in box for what effect it applies on use, if any.

> ###### Action: Offensive
> *A melee attack. Initiating an attack creates a template before the attacker, tokens caught in the template are attacked.*  
> *Some attacks force movement on the attacker. This can be used for effects like if a spear wielder aims the tip forward and charges. The template would be a straight line stretching to five tiles from the user the user and the movement would move the user forward by five tiles.*
> - **Within its rules tab:**
> - Fields for HP damage, BREAK, and knockback (in tile units)
> - An "Action,Reaction" dropdown, next to a "one,two,three" dropdown. If "reaction" is selected, then "one,two,three" does not display.
> - A checkbox for "self-forced movement?", a field for how far to move self, and dropdowns for in which direction relative to token facing you move in.
> - the template in which its attack effects.
> - A drop-in box for what effect it applies on hit, if any.

> ###### Action: Defensive
> *A defensive action reacts to incoming attacks.*  
> *Like an enchanted shield that when struck, deflects half of the attack power back at the attcker.*  
> *Or for a grappler's skill which waits for the opponent to attack first before dodging through and tackling.*
> - **Within its rules tab:**
> - How many attacks this action is effective for. The action won't apply to any more attacks than this number for this round.
> - Fields for HP damage, BREAK, and knockback (in tile units)
> - An "Action,Reaction" dropdown, next to a "one,two,three" dropdown. If "reaction" is selected, then "one,two,three" does not display.
> - A checkbox for "self-forced movement?", a field for how far to move self, and dropdowns for in which direction relative to token facing you move in.
> - the template in which its attack effects.
> - A drop-in box for what effect it applies on activation, if any (self)
> - A drop-in box for what effect it applies on hit, if any.

> ###### Action: Passive
> *A passive skill applies an effect for a set period of time. Out of combat, this time is tracked in real minutes. In combat, this time is tracked in timeline steps (seven per round). It's necessary to define both.*
> - **Within its rules tab:**
> - A checkbox for is the effect time unlimited. If checked, the "active for" field will disappear. 
> - How long the skill is active for (two fields, one for minutes and one for actions)
> - Write the effect applied by this item. *(most likely will just be a json field? PF2E's foundry port has a very comprehensive implementation)*

> ###### Action: Spell
> *It's like an offensive action, except targeted.*  
> *Spells either require a token to target, or they can be placed anywhere. So long as its within sight and so long as its within the maximum distance set in rules.*   
> *Spells place lingering templates on the field. A spell's primary function is to crowd control by corralling enemies. Mages create stage hazards.*
> - **Within its rules tab**:
> - A checkbox for "Can the spell be passed through". If unchecked, it creates invisible walls along its template.
> - A checkbox for "Requires target".
> - A field for maximum distance away from the caster that the spell can be placed (in grid units).
> - The shape of the template.
> - An effect can be chosen to be applied to tokens passing through the spell.
> - If an effect asks for a roll check, then passing through a spell by means of an enemy's knockback immediately results in the worst outcome. While passing through the spell by means of your own skill's forced movement immediately results in the best outcome.
###### about its sheet:
I don't have a clear picture so I don't wanna waste time by trying to have something to put here! Will be in the mockups.


---

### Character item: "Training"
###### description:
*Trainings are the primary method of character growth.*
*Trainings grant characters effects, access to items, special windows like component spellcasting or crafting.*

*Trainings can only be held in a character's repertoire tab. Trainings are the only thing that a repertoire tab can hold. Trainings within the repertoire tab appear as item cards*  
###### about its sheet:
- Its header has no left-side icon.
- Its header is fully backed by a banner image.
- It has a description tab, an effects tab, and a rules tab.
##### a tally of its tabs:
- description
- effects
- rules

## Documents, actors

> #### Actors list
> - [Actor](#actor)
> - [Monster](#monster)
> - [Vehicle](#vehicle)
> - [Loot](#loot)
> - [Deployable](#deployableactor)
> - [Point of Interest](#pointofinterest)
> - [Project](#project)

---

### Actor <a name="actor"></a>
##### Overview  
*The human character type.*  

An actor's sheet has a prominent weapon slot. When a weapon is inserted into the slot, the actions contained in the weapon fill out on the character sheet below the slot.  
Actors have stats.  
An equipment panel with slots for head, chest, shoulders, arms, hands, waist, legs, feet. Two slots each for neck, and wrist. Ten slots for rings.  
The sheet also has an inventory with six slots. These initial six slots are special and have different properties than slots added by storage items.
The character sheet has a repertoire tab, where training items are stored and displayed in item cards that can be dragged and rearranged by the player.  
There's also an "active effects" tab which displays all passive actions currently stored on the actor.  
The "actions" tab which lists all maneuvers, offensive, defensive, and spell action items stored on the actor, except those registered by a weapon. A GM can manually drag action-items into a character sheet's actions tab.
##### Highlights
- Stats block
- Weapon slot
- Equipment display
- Inventory
- Actions tab
- Active Effects tab
- Repertoire tab

---

### Monster <a name="monster"></a>
##### Overview  
*The character type for all things meant to be battled.*  

It has stats, an active effects tab, an actions tab.  
Its sheet features two types of inventory, both of them act as loot lists.  
The first is for guaranteed drops, and acts like a regular inventory. The second is for random chance drops and works by dragging a rollable table into its field to link it.  
The monster token can also configure extra "parts," which are secondary tokens with linked movement. Extra parts can be used to denote the tail of a dragon, the limbs of a giant, etc.
##### Highlights
- Stats block
- Active Effects tab
- Actions drag-in
- Guaranteed loot inventory
- Random drop rollable table
- Extra limbs
---

### Vehicle <a name="vehicle"></a>
##### Overview  
Is similar to the monster type, except its linked to a scene. Players nearby a vehicle token can interact with it to enter it. A Vehicle can be locked through its character sheet.
##### Highlights
- Stats block
- Active Effects tab
- Actions drag-in
- Guaranteed loot inventory
- Random drop rollable table
- Scene link & locked doors
---

### Loot <a name="loot"></a>
##### Overview  
Is the type of token that appears to denote an item lying on the floor. When a player drops an item, it appears as loot. Loot can also be placed by the GM for an item which can be picked up off the floor. Players can pick loot up by dragging and dropping the token into their character sheets. The loot sheet displays the item's sheet. Deployables can't create a loot since they create a deployable type token.
##### Highlights
- Double clicking the token opens the appropriate items sheet

---

### Deployable <a name="deployableactor"></a>
##### Overview  
The token version of the [Deployable](#deployableitem) item.

---

### Point of Interest <a name="pointofinterest"></a>
##### Overview  
Can be configured in two modes: Vista and Gathering point. In vista mode, interacting with a POI token will display a linked journal entry. In gathering mode, a POI token has four fields: tool tags, yield, integrity, table. Tool tags is just a tag input field. The gathering point will only accept interaction if a the character has a weapon with matching tags equipped. If no tags are present in the input field, the POI will require no tools. Yield is percentage chance to gain more items on interaction. If set to 0, the player will always get 1 item. If set to 150, players will always get 2 items with a 50% chance to get 3. Integrity is a simple number of uses before the POI token disappears and its sheet force closes. Table is a table of possible drops. Its linked just like a monster's loot table.

---

### Project <a name="project"></a>
##### Overview  
Is an interactable marker that displays progress toward a goal. It can be configured to ask for items or money, and players can contribute to it.

---
