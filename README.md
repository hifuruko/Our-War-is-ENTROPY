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

That concludes the combat rules. The document types: All documents have a rules tab, which is an isolated module that gets imported into each sheet. Some sheets have more to the rules tab, but all will have a field to view the document's UUID.

Stats are managed by an isolated module that gets imported to each sheet type. The following are treated the same: the rules tab, a character's inventory, active effects tab, actions tab, an item's description tab, effects tab, price field.

## Documents, actors

#### Actor
The human character type. An actor's sheet has a prominent weapon slot. When a weapon is inserted into the slot, the actions contained in the weapon fills out on the character sheet below the slot. Actors have stats, and an equipment panel with slots for head, chest, shoulders, arms, hands, waist, legs, feet, two slots for neck, wrist, ten slots for rings. The sheet also has an inventory with six slots. These initial six slots are special and have different properties than slots added by storage items. The character sheet has a repertoire tab, where training items are stored and displayed in item cards that can be dragged and rearranged by the player. There's also an "active effects" tab which displays all effects currently on the actor. The "actions" tab which lists all action-type items the character can use, including those registered by a weapon. A GM can manually drag action-items into a character sheet's actions tab.

#### Monster
The character type for all things meant to be battled. It has stats, an active effects tab, an actions tab. Its sheet features two types of inventory, both of them act as loot lists. The first is for guaranteed drops, and acts like a regular inventory. The second is for random chance drops and works by dragging a rollable table into its field to link it. The monster token can also configure extra "parts," secondary tokens with linked movement. Extra parts can be used to denote the tail of a dragon, the limbs of a giant, etc.

#### Vehicle
Is like monsters, except its linked to a scene. Players nearby a vehicle token can interact with it to enter it. Vehicles can be locked through their character sheets.

#### Loot
Is the type of token that appears to denote an item lying on the floor. When a player drops an item, it appears as loot. Loot can also be placed by the GM for an item which can be picked up off the floor. Players can pick loot up by dragging and dropping the token into their character sheets. The loot sheet displays the item's sheet. Character items can't create a loot. Deployables can't create a loot either since they create a deployable type token.

#### Deployable
Is the type of token that appears when a deployable item is dropped by the player, similar to loot except they have a specific function. A tent kit could create a set of tiles and then delete them afterwards. A turret could set the player stationary and give them a special attack. Because of how vastly different each type of deployable could be, it should be freely programmable. The deployable sheet has three extra sections in the rules tab: "javascript" "handlebars" "css" where you program the deployable and its sheet. For a GM, the sheet that's created by the rules tab gets wrapped into a viewable form inside the deployable sheet. For a player, they see only the sheet created by the rules tab.

#### Point of Interest
Can be configured in two modes: Vista and Gathering point. In vista mode, interacting with a POI token will display a linked journal entry. In gathering mode, a POI token has four fields: tool tags, yield, integrity, table. Tool tags is just a tag input field. The gathering point will only accept interaction if a the character has a weapon with matching tags equipped. If no tags are present in the input field, the POI will require no tools. Yield is percentage chance to gain more items on interaction. If set to 0, the player will always get 1 item. If set to 150, players will always get 2 items with a 50% chance to get 3. Integrity is a simple number of uses before the POI token disappears and its sheet force closes. Table is a table of possible drops. Its linked just like a monster's loot table.

#### Project
Is an interactable marker that displays progress toward a goal. It can be configured to ask for items or money, and players can contribute to it.


## Documents, Items 

All items are subject to a universal tagging system. Tags are managed by a centralized tag manager, accessible through system settings, and are used to manage several rules. Like, which items can be dragged into which slots or which items are inert outside of which slots. Tags appear as a small text field inside the header, underneath the item's name. In the rules tab, items have a "hidden tags" section, which has the same function as the header tags section. Tags always appear as chip inputs wherever they are. Right clicking a tag toggles its display between its label and its UUID. The tag input field, the tagging system, are all isolated modules that get imported in.

#### Physical item: "Material" 
Is an inanimate item type. Its item sheet is made of two panels: Its image, which spans the left side of the sheet. And the description and rules tabs, on the right. It also has a price field, which exists as a footer in the right side panel.

#### Physical item: "Weapon" 
A weapon's item sheet has a field to drag and drop Action items. They'll display as action cards within the item sheet. This is effectively an item's effects tab, without the tab. If you can import the effects tab without displaying a tab, that would be wonderful. A weapon has a price footer.

#### Physical item: "Tool" 
Tools are a general purpose for any item which used. A bomb, a trap kit, a magnifying glass, for some examples. Its sheet looks like a material's sheet except it has an Effects tab. In the rules tab, there's a checkbox for inert. If this is checked, actions held in the tool's effects tab won't appear in the player's actions tab.

#### Physical item: "Storage" 
Storage items grant extra slots in a player's inventory. Within the rules tab is an equipment checkbox. If toggled, then the storage item must be placed in an equipment slot or else it'll be inert. Even if equipment is unchecked, storage items must be placed in one of the original six inventory slots or be inert. Also in the rules tab is a "has inventory" checkbox and a "can be carried" checkbox. If has inventory is checked, the item sheet will gain an inventory tab which mirrors what's placed in the inventory slots granted by the item in the actor's inventory. Removing this item from the player's inventory and placing it on the canvas will take its stored items with it, changing it into something more like a chest. If "can be carried" is unchecked, it can only store items while in canvas form. Moving a storage with "can be carried" unchecked into the player's inventory will result in its items dropping onto the canvas. The player may drop the storage down to use it as normal. When a player hovers over a storage item in their inventory, the slots it adds is highlighted. That way, you can keep track of what exists where.

#### Physical item: "Consumable" 
Consumables look like a tool sheet, except above the right side panel, there's a panel above it with a prominent "Use" button. And to the right of that button, a charges display with how many maximum uses an item has versus how many uses it has left. The use button casts the action held in the effects tab and prints the effect's item card to chat along with a "Character used:". In the rules tab, there's a checkbox for Refillable. If refillable is not checked, then an item's uses dropping to 0 by means of clicking the use button will result in that item disappearing from the player's inventory and the item sheet force closing. The panel containing a consumable's use button will only appear if either the item is inside the using player's inventory or if the player's token is within 5ft of the consumable's loot token.

#### Physical item: "Equipment"
Equipment items look like a tool sheet. Equipment is inert until placed in a character's equipment slot. 

#### Physical item: "Kit"
A kit is an item which stores other items for immediate use.

#### Physical item: "Deployable"
The item version of a deployable. Can be stored in inventories. When dragged onto the canvas, will result in a deployable-type token.

#### Character item: "Action"
Can be configured in several modes: Maneuver, Offensive, Defensive, Passive, Spell. 
> ###### Action: Maneuver
> A maneuver can be configured in its rules tab, if it's unavailable in combat, how many (if any) actions it costs, and what effect it applies.

> ###### Action: Offensive
> This is a melee attack. Within its rules tab, can be configured how how much it deals in HP damage, BREAK, knockback in tile units, self-forced movement and in which direction, the template in which its attack effects, the effect (if any) which is applied to tokens struck by the attack, if this is a reaction (checkbox), how many actions this attack consumes.

> ###### Action: Defensive
> A defensive action reacts to incoming attacks. In its rules tab, can be configured if it's a reaction (checkbox), how many actions it costs, how many attacks it can activate for (it simply won't apply to any more attacks than this number for this round), what effect is applied when the action activates, and if the action can be targeted onto another token.

> ###### Action: Passive
> A passive skill applies an effect for a set period of time. Out of combat, this time is tracked in real minute. In combat, this time is tracked in timeline steps (seven per round). It's necessary to define both. Within its rules tab is configurable how long the skill is active for (two fields, one for minutes and one for actions) and what effect the skill applies. 

> ###### Action: Spell
> It's like an offensive action, except targeted. Within its rules tab, can be configured if it requires a token to target. If that's not checked, then the spell can be placed anywhere, so long as its within sight and so long as its within the distance later set in the rules tab. What is also set is the maximum distance away from the caster that the spell can be placed. The shape of the template. As well as if the spell can be passed through, which is a checkbox. An effect can be chosen to be applied to tokens passing through the spell. If an effect asks for a roll check, then passing through a spell by means of an enemy's knockback immediately results in the worst outcome. While passing through the spell by means of your own skill's forced movement immediately results in the best outcome.

#### Character item: "Training"
Trainings can only be held in a repertoire tab. Trainings are the only thing that a repertoire tab can hold. Trainings have an effects tab, and so any effectives held by a training will apply to the character holding it. Trainings within the repertoire tab appear as thin cards previewing their image and description. Trainings can be dragged and rearranged within the repertoire tab, but players cannot remove a training item.

---

The following can only be changed by a GM, players will see a non-editable version of it:
The tag input field, the price field, editing actions, description text boxes, a kit's inventory.


The following will only appear to a GM:
The rules tab.
