# Storage & Inventory

One incredibly important aspect of this design is the way objects are stored in-world, instead of simply in some abstract user interface that pops up upon interacting with a container.

First of all, any item takes up a certain amount of space in a so called "storage space". Storage space, similar to block space and micro-block space is made up of voxels. Items may take up a certain number of such voxels in any shape.

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

The storage space an item takes up roughtly represents the size and shape of that item, but doesn't have to match it 100%. When stored, an item might be shrunk slightly for convenience purposes.

Additionally, storage voxels inside a container might also be shrunk slightly for convenience. For example if an empty block (1m³) had a storage space of 6³, each voxel would be ~0.17m³ in size. Meanwhile a chest with an internal size of 0.75m³ could have a space of 5³, which would result in a voxel size of 0.15m³. The items stored in a chest would be scaled down slightly to fit.

## Player Storage / "Inventory"

Inventory space, compared to other games, is practically non-existant. Starting out, players may only pick up things with their hands, and carry stuff on their back.

### Carrying

A player can pick up any container with their hands and move it around, and with it any items that are stored inside it.

Depending on the size and weight of the container, it may have to be carried with both hands, prevent the player from performing certain movement actions, possibly even slowing them down dramatically.

When taking damage, the container will be dropped to the ground.

### Equipping

It is also possible to strap a container to your back, for example using a length of rope. Depending on size and weight, it may restrict you similarly to carried ones, though to a smaller degree.

Thus it is useful to instead use containers made specifically for carrying on your back, such as backpacks, which will restrict you less. Larger backpacks come with slots to attach smaller items and tools on the side and front.

### Equipment

Beyond backpacks there is also a number of other items that increase the amount of items that can be carried with on one's character.

- **Clothes** - Certain clothing items could have pouches to store small items.
- **Belt** - Attach smaller items (small bags, bottles) using string.
- **Sheath / Holster** - Attach on belt and insert tools and weapons.
- **Quiver** - Carry on your back or attach to belt to store arrows / bolts.

## Interaction

Regardless of whether a container is placed in the world, carried or equipped by a player, anyone can still interact with it. This would allow players to collaborate more easily, but could also be used to steal from unsuspecting people.

## Vehicles

Multiple containers may be placed on a vehicle such as a cart and then either pulled by a player or trained animal.

## Liquid Storage
