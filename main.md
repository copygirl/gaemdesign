# Gameplay

## Controls

| Key      | Description |
| -------- | ----------- |
| `Mouse`  | Look around. Depending on your current action and held object, character turn speed might be limited. |
| `WASD`   | Walk. |
| `Space`  | Hold to jump higher, then release. Slows you down while you're charging your jump. |
| `Shift`  | Sprint. Uses stamina, similar to other actions. |
| `Ctrl`   | Walk / sneak (different animation depending on stance). Reduces the amount of sound you make. |
| `Tab`    | Switch stances (**Passive** / **Combat**). Draws the weapons you were holding last or puts them away if possible. |
| `Tab` x2 | Switch to **Combat** stance and draw sheathed / equipped weapons, dropping whatever you were holding. |

### Advanced movement

| Key | Description |
| --- | ----------- |
| `Ctrl` + `Shift` | Hold for some time to start crawling. Automatically exits **Combat** stance. Hold `Space` to stand up again. |
| `Shift` + `WASD` x2 | Short dash, with minor short slowdown afterwards. |
| `Shift` + `WASD` x2 + `Space` | Long dash, with medium, slightly longer slowdown afterwards? |
| `Ctrl` + `WASD` x2 | Roll? |

Depending on your equipment and held objects, certain movement options might
not be available or you will be slowed down, for example when carrying a heavy
object.

### Held objects

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
your hands will be swapped out with each other. Holding the mouse buttons
instead will attempt to use both hands together. (Such as combining objects,
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

## Voxel crafting

As you're starting an individual micro-block "project", and possibly upon
request, show a list of available recipes. Upon selecting one of these, show
a highlight / wireframe of the target shape.

Some of the crafting systems may behave like little puzzles, requiring you to
experiment with and learn a set of steps, possibly refining it as you gain
experience as well as access to new tools and automation.

### Knapping

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
to "break through" and remove the desired shape.

Depending on the tool head being made, certain number of voxel layers 

### Clay shaping

Unlike knapping, clay shaping is freely three-dimensional, and materials won't
be lost if you make a mistake. Also has much different crafting mechanics.
There's different "techniques" to manipulating clay:

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



### Smithing



## Heating

## Melting


# Progression

## Tiers

- Stone
- Copper
- Bronze
- Iron
- Steel

# Survival

## Food

## Farming

## Health


# Building




# Combat




# World generation
