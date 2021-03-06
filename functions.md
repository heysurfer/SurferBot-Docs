# Functions
* [getBot](#getbot)
* [sendPacket](#sendpacket)
* [SendPacketRaw](#sendpacketraw)
* [findPath](#findpath)
* [getLocal](#getlocal)
* [getInventory](#getinventory)
* [getPlayers](#getplayers)
* [getObjects](#getobjects)
* [getTile](#gettile)
* [getTiles](#gettiles)
* [getItemInfo](#getiteminfo)
* [isSolid](#issolid)
* [isSeed](#isseed)
* [canHarvest](#canharvest)
* [placeTile](#placetile)
* [hitTile](#hittile)
* [wrenchTile](#wrenchtile)
* [warp](#warp)
* [move](#move)
* [setPos](#setpos)
* [say](#say)
* [runThread](#runthread)
* [getAllBot](#getallbot)
* [connect](#connect)
* [useDoor](#usedoor)
* [isInside](#isinside)
* [collectObject](#collectobject)
* [inWorld](#inworld)
* [itemExist](#itemexist)

## getBot
`getBot(string botname)`

Return bots from list

Example:
```lua
bot = getBot("growid")
bot:sendPacket("action|respawn", 2)
```


## sendPacket
`sendPacket( string packet, int type)`

Sends text packet with selected type to client .

Example:
```lua
-- Sends respawn packet to server
sendPacket("action|respawn", 2)
```

## sendPacketRaw
`sendPacketRaw( GamePacket packet)`

Sends [GamePacket](Structs.md#gamepacket) to server.

Example:
```lua
-- Sends wear clothing packet to server
packet = {}
packet.type = 10 
packet.int_data = 48 -- Clothing ID (Jeans)
sendPacketRaw(packet)
```

## findPath
`findPath(int x, int y)`

Finds path to selected x,y

Example:
```lua
-- Finds path to top left corner of the world
findPath(0, 0)
```

## getLocal
`getLocal()`

Returns local [NetAvatar](#Structs.md#netavatar) struct

Example:
```lua
-- Logs local players name
me = getLocal()
log(me.name)
```

## getInventory
`getInventory()`

Returns table of [InventoryItems](Structs.md#inventoryitem)

Example:
```lua
-- Logs all item ids in your inventory
for _,cur in pairs(getInventory()) do
log(cur.id)
end
```

## getPlayers
`getPlayers()`

Returns table of [NetAvatars](Structs.md#netavatar)

Example:
```lua
-- Logs current worlds players names
for _,player in pairs(getPlayers()) do
log(player.name)
end
```

## getObjects
`getObjects()`

Returns table of [WorldObjects](Structs.md#worldobject)

Example:
```lua
-- Logs current worlds objects item id's
for _,object in pairs(getObjects()) do
log(object.id)
end
```

## getTile
`getTile(int x, int y)`

Returns world [Tile](Structs.md#tile) in selected position

Example:
```lua
-- Logs top left corners foreground block id
tile = getTile(0, 0)
log(tile.header.fg)
```

## getTiles
`getTiles()`

Returns table of [Tiles](Structs.md#tile)

Example:
```lua
-- Logs current worlds all foreground block id's
for _,tile in pairs(getTiles()) do
log(tile.header.fg)
end
```

## getItemInfo
`getItemInfo(int itemid)`

Returns [ItemInfo](Structs.md#iteminfo) of selected Item ID

Example:
```lua
-- Logs Item ID 2's name (Dirt)
log(getItemInfo(2).name)
```

## isSolid
`isSolid(int x, int y)`

Returns true if block is solid and false if its not

Example:
```lua
if isSolid(0, 0) then
log("Tile 0, 0 is solid")
else
log("Tile 0, 0 is not solid")
end
```

## isSeed
`isSeed(int x, int y)`

Returns true if tile is seed , false if its not

Example:
```lua
if isSeed(0, 0) then
log("Tile 0, 0 is Seed")
else
log("Tile 0, 0 is not Seed")
end
```

## canHarvest
`canHarvest(int x, int y)`
Returns true if tile is harvestable , false if  not

Example:
```lua
if canHarvest(0, 0) then
log("Tile 0, 0 is harvestable")
else
log("Tile 0, 0 is not harvestable")
end
```


## hitTile
`hitTile(int x, int y)`

Send Punch Packet To X,Y

Example:
```lua
---Punch To 0,0
hitTile(0,0)

```

## wrenchTile
`wrenchTile(int x, int y)`

Send Wrench Packet To x,y

Example:
```lua
---Wrench To 0,0

wrenchTile(0,0)

```

## placeTile
`placeTile(int x,int y,int blockid)`

Place Block To x,y

Example:
```lua
---Place Dirt To 0,0
placeTile(0,0,2)

```

## warp
`warp(string x)`

Warp To x

Example:
```lua
warp("BUYGHC")

```

## Move
`move(enum MOVE,int speed)`

Example:
```lua
-- Speed Default Value 1, Max Value 4
move(RIGHT,1)
move(LEFT,1)
move(UP,1)
move(DOWN,1)
```

## setPos
`setPos(int x,int y)`

Example:
```lua
--- Sets bot position
setPos(0,0)
```
## say
`say(string text)`

Example:
```lua
-- Send chat message
say("Hello")
```

## runThread
`runThread(function() 
//code here
end)`

Example:
```lua
runThread(function()
while true do
log("New Thread")
end
end)

while true do
log("Normal Thread")
end
```
## getAllBot

Example:
```lua
for k,v in pairs(getAllBot) do 
v:Say("hi")
end
```

## connect
`connect(string growid,string password,bool VdsSupport)`

Example:
```lua
connect("mygrowid","mypassword",false)
```


## useDoor
`useDoor(int x,int y)`

Example:
```lua
useDoor(0,0)
```

## isInside
`isInside(int x,int y,int rad)`

Example:
```lua
if isInside(0, 0,5) then
log("x 0, y 0 is in inside")
else
log("x 0, y 0 is not inside")
end
```

## collectObject
`collectObject(int uid)`

Example:
```lua
-- Collecting Object With UID
collectObject(0)
```
## inWorld
`inWorld()`

Example:
```lua
if inWorld() then
log("in world")
else
log("not in world")
end
```

## itemExist
`itemExist(int itemid)`

Example:
```lua
if itemExist(2) then
log("Dirt Exist In Inventory")
else
log("Dirt Not Exist In Inventory")
end
```

