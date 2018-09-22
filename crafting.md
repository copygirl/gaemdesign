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
