---
title: onPlayerDied
---

Name
----------
```
baseevents:onPlayerDied
```

Parameters
----------

```
int killerType, array deathCoords
```

- **killerType**: The pedType of the ped that killed this player. (View the screenshot below for available pedTypes)
- **deathCoords**: An array containing the x, y, z coordinates of where the player died.


##### Ped types
![](/ped_types.png)

Examples
--------

This example print all the data about the player death

```lua
AddEventHandler("baseevents:onPlayerDied", function(killerType, deathCoords)
    PlayerNotify("Killer type: " .. killerType)
    -- will be -1 if you are killed by a NPC

    PlayerNotify(GetPlayerName(PlayerId()).." died")
    
    local streetHash, _ = GetStreetNameAtCoord(deathCoords[1], deathCoords[2], deathCoords[3])
    PlayerNotify("Player died at " .. GetStreetNameFromHashKey(streetHash))
end)
```
Result
--------
![](https://i.imgur.com/qdMDLw7.png)

