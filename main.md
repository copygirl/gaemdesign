# Introduction

This is a design documentation for my dream game and ideas I would like to
realize in it, regardless of feasibility. Since the game has yet to have been
made, except for a couple of fruitless attempts at creating an engine of sorts
that would support it, as well as my perfectionism, I figured I'd at the very
least would create this document / repository to write down my design ideas as
detailed as I can.

Note that I have absolutely no problem if anyone were to take inspiration or
straight up implement some or all of these ideas into their own game. I'm very
much a proponent for sharing ideas and I believe more implementations allow
greater refinement and remixing which allows for even more impressive games to
be made! (Not to mention the low probability that I will actually do this.)

For the curious, there's also an [older design document][DesignDoc] for the
same basic game idea which you're free to check out. It may not 100% reflect my
current ideas and goals, but it currently contains some information not yet
present here, so it may still be of interest to you.

[DesignDoc]: https://copy.mcft.net/redirect/DesignDoc

## Core Ideas

- **Open source**, open development and modding friendly
- **First-person** with own character model visible when looking down, holding
  items and performing actions.
- **Multiplayer voxel sandbox** with survival aspects. Block grid size is 1m³.
- Focus on **progression** and **collaboration** with in-depth **crafting**,
  **customization** and **building**. Things take time, though ideally without
  unjustified grinding.
- **No GUIs** and minimal to no HUDs. Crafting and storage is done in-world.
- **No character progression / stats / skills** that would artificially gate
  players from accessing content or give them invisible numerical advantages
  over other players. You progress by gaining access to new tools and
  technology. You "level up" by improving your motor skills, knowledge and
  experience as a player, rather than a character.

## Settings

This document mainly outlines a game more focused on a medieval survival
fantasy setting, possibly sneaking into the territory of steampunk and magic
as late-game content. Likely with very little to no pre-made civilization
beyond what players will construct in their time.

Yet I also yearn for an apocalyptic style setting that has players exploring
vast semi-destroyed cityscapes, scrapping old machinery and electronics for
raw resources to advance. I mention this as lots of the mechanics could be
shared between both games.


# Gameplay

## Controls

### Basic movement

| Key      | Description |
| -------- | ----------- |
| `Mouse`  | Look around. Depending on your current action and held object, character turn speed might be limited. |
| `WASD`   | Walk. |
| `Space`  | Hold to jump higher, then release. Slows you down while you're charging your jump. |
| `Shift`  | Sprint. Uses stamina, similar to other actions. |
| `Ctrl`   | Walk / sneak (different animation depending on stance). Reduces the amount of sound you make. |
| `Tab`    | Switch stances (**Passive** / **Combat**). Draws the weapons you were holding last or puts them away if possible. |
| `Tab` x2 | Switch to **Combat** stance and draw sheathed / equipped weapons, dropping whatever you were holding. |

### Advanced Movement

| Key | Description |
| --- | ----------- |
| `Q` / `E` | Leaning. Allows you to look around corners, just sticking out your head. (Only in **Passive** stance?) |
| `Ctrl` + `Shift` | Hold for some time to start crawling. Automatically exits **Combat** stance. Hold `Space` to stand up again. |
| `Shift` + `WASD` x2 | Short dash, with minor short slowdown afterwards. |
| `Shift` + `WASD` x2 ➡ `Space` | Long dash, with medium, slightly longer slowdown afterwards? |
| `WASD` x2 ➡ `Ctrl` | Roll? |

Depending on your equipment and held objects, certain movement options might
not be available or you will be slowed down, for example when carrying a heavy
object.

### Hand Interaction / Held Objects

Character is two-handed, each mouse button controls one hand. It is possible to
carry large and/or heavy objects with both hands. Different modifier keys
affect how the held object is used. The modifier key only needs to be held when
you press the mouse button. You may let go off the key afterwards to prepare a
different type of action.

| Modifier           | Description |
| ------------------ | ----------- |
| None (Passive)     | Use. (This will never hurt entities to avoid accidents.) |
| None (Combat)      | Attack. Hold to **charge**. (Move mouse to **swipe** a certain direction?) |
| **Interact** (`F`) | Pick up / place down / switch. Highlights possible objects to interact with. Depending on the size / weight of the object, this may take some time. |
| **Throw** (`T`)    | Drop. Hold to **throw**. Distance depends on weight. |

Pressing **Interact** followed by clicking both mouse buttons, the objects in
your hands will be swapped out with each other. Holding the mouse buttons will
instead attempt to use both objects together. (Such as combining them, or
taking an item out of a pouch with an empty hand, ...)

For most items, an ongoing action, especially ones that are charged up and are
waiting for you to release the mouse button, can be cancelled by pressing the
other mouse button at the same time. As such, there's only very few special
items which may be used at the same time.

One exception to this rule is for example shields. Another item can be used
while the shield is being used (held up to block). However, if you're charging
an attack, pressing the button for the shield will cancel that attack, instead.

For objects held with both hands, both buttons must be held down.


# Crafting

## Tools

| Category     | Material    | Description |
| ------------ | ----------- | ----------- |
| **Smash**    | Many        | Breaks things into smaller bits, possibly dust. Useful for early game resource collection, not any meaninful precision work. |
| **Shape**    | Stone/Metal | Changes the shape of things, either by breaking off parts or hammering metal into the desired shape. Material loss depends on a number of factors. |
| Shape (Soft) | Soft        | Clay or similar soft and sticky materials may also be shaped by hand. |
| **Chop**     | Wood/Plant  | Breaks apart wooden things, possibly into smaller pieces. Also allows for harvesting plants in a crude way. |
| **Mine**     | Stone       | More effective alternative to **Smash** for breaking stone materials and ores. |
| **Cut**      | Plant/Food  | More precise alternative to **Chop** for harvesting plants, animals, preparing food and fine crafting. |
| **Dig**      | Soft        | For moving around soft ground materials. |
| **Saw**      | Wood/Stone  | Even more precise alternative to **Chop** / **Mine** for quick crafting of certain shapes. |
| **Carve**    | Wood/Stone  | Even more precise alternative to **Chop** / **Mine** for fine crafting. May require a **Smash** tool to drive the object into the material. |
| **Sharpen**  | Stone/Metal | Increases the sharpness and therefore effectiveness of a tool / weapon. The sharpened tool loses some of its material, depending on hardness, permanently reducing its weight / durability. |

## Attaching

By holding an item over another item which has a recipe defined to combine
both, a highlight will be shown where the held item may be "attached". If
there's no space for the item, the highlight will be red.

| Attachment Type | Description |
| --------------- | ----------- |
| **Temporary**   | After placing a temporary attachment, either side of the attachment may simply be taken away as their individual pieces. The recipe will always be unfinished after one of these steps. |
| **Binding**     | Applying a binding attachment connects the binding part and one or more other parts, either permanently or in such a way that the binding has to be removed first. A binding recipe may result in a finished, usable tool or item. |

## Heating

Objects will slowly change their own temperature depending on the surrounding
heat. This can affect items such as food, causing them to rot faster at warmer
temperatures, get cooked when hot, or get burned to ash when extremely hot.

Objects made out of metal become malleable when applying enoug heat, allowing
to shape them with a hammer. (See **Smithing**.)

### Melting

Objects made out of metal may melt at significantly hot temperatures and behave
like a viscuous fluid before they cool down again. Molten metals may be poured
into a cast to form specific shapes. (See **Casting**.)

## Voxel Crafting

As you're starting an individual micro-block "project", and possibly upon
request, show a list of available recipes. Upon selecting one of these, show
a highlight / wireframe of the target shape.

Some of the crafting systems may behave like little puzzles, requiring you to
experiment with and learn a set of steps, possibly refining it as you gain
experience as well as access to new tools and automation.

Certain recipes might also be dynamic in some ways in that they allow different
resulting sizes of some objects. While being identical in basic functionality,
they may have different stats such as weight, durability and effectiveness at
specific tasks.

### Knapping / chiseling

Stone materials can be **shaped** into a different form using a hammer, pick,
chisel, hard rock or similar. rock, breaking off smaller pieces.

| Tool        | Size  | Shape |
| ----------- |:-----:|:-----:|
| Large Rock  | 4x5x3 |   ◯   |
| Medium Rock |  3x4  |   ◻   |
| Small Rock  |  2x3  |   ◻   |
| Sharp Rock  |  1x2  |   –   |
| Pick        | 3x3x3 |   +   |
| Hammer      |  2x2  |   ◻   |
| Chisel      |  1x1  |   ·   |
| Saw         |  1x∞  |   ―   |

```
 ##   ###  ##  #
#OO#  ###  ##  #
#OO#  ###  ##
#OO#  ###
 ##

 #   ##  #  ^
#O#  ##     #
 #          #
            v
```

When using lower quality tools such as rocks, multiple attempts may be required
to "break through" and remove the desired shape. Breaking off larger pieces of
stone may result in a small rock to be created.

Depending on the recipe, an item has to be made from varying numbers of layers.
For example, a stone knife blade would only be 1 layer thick while an axe head
may be 3 layers. It may be required to flip the working piece to shape the
opposite side.

This technique may also be used to create items and blocks that have varying
shapes for purely decorative purposes.

### Clay Shaping

Clay shaping is freely three-dimensional, materials can be added and removed;
they won't be lost if you make a mistake. Also has much different crafting
mechanics from knapping.

Here are some different "techniques" to manipulate clay:

| Category   | Technique | Description |
| ---------- | --------- | ----------- |
| **Add**    | Single    | Adds a single voxel anywhere. |
|            | Line      | Adds an axis-oriented line to any continuously flat part. |
|            | Layer     | Adds a horizontal layer over an area. If there's free space under a voxel, it may move "fall" to one voxel downwards. |
| **Remove** | Single    | Takes away a single voxel anywhere. |
|            | Squach    | Gradually squashes all connected voxels together into a generic ball, destroying the shape and eventually picking up the raw material. |
| **Mold**   | Press     | Continuously presses against a flat surface, pushing voxels away from the pressure point up to 2 voxels outwards. |

Using a turntable the process of forming "round" clay objects such as bowls
and pots becomes much easier and faster. It does this by rotating and mirroring
all actions 8 times.

Individual voxels of clay must be supported sufficiently, otherwise they will
slide down after a short amount of time.

### Casting

Using temperature resistant materials such as fire clay to create a cast and
then firing it creates a cast that can be used multiple times to pour molten
metal for it to cool and harden.

Tools that require sharpening to be effective will be completely dull at first
so they have to be worked quite a long time to be decently useful. This is
unlike knapping, which will at least create semi-shapened tools.

### Smithing

When a metal is heated to a certain temperate it becomes soft and malleable,
such that a hammer of sufficient quality can shape the metal by hitting it
multiple times. The hot metal needs to be picked up and carried using a pair of
tongs, and might need to be heated back up to temperature multiple times in
order to finish the recipe.


# Storage

One incredibly important aspect of this design is the way objects are stored
in-world, instead of simply in some abstract user interface that pops up upon
interacting with a container.

First of all, any item takes up a certain amount of space in a so called
"storage space". Storage space, similar to block space and micro-block space
is made up of voxels. Items may take up a certain number of such voxels in any
shape.

```
Scythe  Axe  Shield
======  ===  ======
 #####   ##   ####
 #####   ##   ####
 #       #    ####
 #       #    ####
 #       #     ##
 #
 #    Rocks
 #    =====  ##
     ## ### ####
     ## ### ####
        ###  ##
```

The storage space an item takes up roughtly represents the size and shape of
that item, but doesn't have to match it 100%. When stored, an item might be
shrunk slightly for convenience purposes.

Additionally, storage voxels inside a container might also be shrunk slightly
for convenience. For example if an empty block (1m³) had a storage space of 6³,
each voxel would be ~0.17m³ in size. Meanwhile a chest with an internal size of
0.75m³ could have a space of 5³, which would result in a voxel size of 0.15m³.
The items stored in a chest would be scaled down slightly to fit.

Since inventory space, compared to other games, is practically non-existant, it
becomes incredibly important to be able to move containers around. Usually, a
character would not be able to carry 10 different items around. Though if they
first place them in a container such as a chest, barrel or similar, they can
pick up said container with their hands and move it around. It may also be
possible to strap a container to your back. From then, multiple containers may
be placed on a vehicle such as a cart and then either pulled by a player or
trained animal.


# Building




# Survival

## Food

## Farming

## Health

Instead of a single scalar value as health, create a system in using which
multiple wounds and other negative status effects can affect your ability to do
certain tasks.

Instead of dying, there could be a state of unconsciousness before a character
would die for good. Blood loss, poisons, lack of oxygen, concussions and
perhaps pain itself could cause you to lose consciousness. All of these factors
would be calculated together to decide whether you're close. For example if you
were to start running after having lost some blood from a wound you took from
falling some distance, the additional lack of oxygen could put you over the
egde and you might pass out.

Time heals all wounds, though caring for your injuries, through applying
healing balms or bandages will greatly shorten the time for this to happen.
Healthy, high quality food, will also slightly speed things up the healing
process as well, regardless of whether you ate before or after taking damage.


# Progression

## Tiers

- Stone
- Copper
- Bronze
- Iron
- Brass
- Steel


# Combat

- When charging up to fire an arrow with a bow, swiping the mouse as you shoot
  will give it some "spin", causing it to arc towards that direction. Might not
  be realistic but definitely pretty cool.


# World Generation
