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
