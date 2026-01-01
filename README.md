# Fight
Fight is a 1v1 Gladiator-style fighting RPG.

You get paired with someone or entity in a pit, you have to fight them to win. You start with bare fists and when you win you can get coins to upgrade your gear. And, if you lose you have to start all over again.

## Mechanics
### State
Players have a state machine connected with their wrapper, which decides whether the player can do certain things.

Players can be 4 different states,
- 'play'
- 'dev'
- 'build'
- 'spectate' 

A Player can fight in 'play' state, but they cannot change the map or build.

This permits the player to do things, in addition to being able to control which transitions a player has access to. This is essentially our version of a permission system with state.
### Stats
Stats are a way to have attribute modifiers of certain statistics in-game, such as damage, range, or even blood stones.

The code architecture behind Stats is too complicated to explain for me right now, I will finish off this explanation later.
### Special Effects
Special Effects are a way for weapons to have abilities that are binded to hotkeys  

### Items
Item struct is a Wrapper around ItemStack, which should be a reference to something within an inventory, like player's tool. You can modify the ItemStack with
```applescript
slot {_item_struct}->slot of {_item_struct}->owner
```
Which should be enough to modify it.
If it's not however, you can set it to a variable, modify the variable, then set that slot to the variable.

All generated item's nbt has a uuid tag which can index a map {-item::%uuid%}, giving us back the Item struct.




