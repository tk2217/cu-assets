CodeUtilities includes Schem2DF, a system that allows you to import various builds to your DiamondFire plot.
In this page, you can learn how to import your own structure files to your DiamondFire plot.

**Importing Structure Files**
A structure file is a file that contains Minecraft builds in it.
First of all, Schem2DF supports these types of structure files:
- .schematic files: A file often created by MCEdit, or older versions of WorldEdit.
- .schem files: A file that can be created using recent versions of WorldEdit.
- .litematic files: A file created by the Litematica mod.
- Standard NBT files: A file created in Structure Blocks.

These four types of structure files can be imported into your DiamondFire plot using Schem2DF.
To use Schem2DF in your CodeUtilities, first you need to place your structure files to `.minecraft/schematics` folder.
Then, go into dev mode in your plot and type `/schem load <filename>` to load the structure file you placed.

Now, the mod loads the structure file you specified, after the loading finishes, you will get some Code Templates in your inventory.
Place the first Code Template (#1) in a new codeline, and place next ones right after the last one. (It should create one long line of Set Variable actions)
After that, rename the function you placed if you want.

Now you have placed the Structure Data Function in your codespace. Next, you need to pass the Structure Data to the Schem2DF Builder to build it into your plot.

Type `/schem builder` to get the Schem2DF Builder. Place down the item you got in your inventory, and grab all Ender Chests inside it.
Place all 5 functions in your codespace. (6th one is a fake item, lol)

At this point, you should have both Structure Data and the Schem2DF Builder in your codespace. Now, it's time to let it build the structure in your plot.

To build your Structure Data, first you need to set the local variable named `base` to the location where you want the structure to be built. Right after that, call your Structure Data function you placed, and finally, call the Schem2DF Builder function.

If you've set up everything correctly, it should start building the structure in your plot.
Now enjoy watching the build process!