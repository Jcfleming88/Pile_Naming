# Pile_Naming
Dynamo Script for producing unique names for piles within Revit

---

This script was created to automate the creation of pile marks within Revit. When run, this script will search for piles within a model, determine which piles are part of the same pilecap and provide unique names for each piles. The script was created in order to automate the naming process when creating piles schules. Piles will be named from the top left to the bottom right.

It may be possible to alter families to name piles within a pilecap and then just name the pilecap (which would make this script a lot faster) but this script was written to use families that had already been produced and the user did not want to change.

---

# Controls

There are a number of options within the script that will help to organise and limit the number of piles that are named

1) Pile Naming Prefix - This is the prefix to the pile number. Pile marks will be "Prefix" + "##". e.g. PC15

2) X and Y Tolerances - The script will initally sort the pile locations within a tolerance grid, meaning that piles a couple of mm high or lower will still be in order. Piles within the same area will then be sorted by their actual location. You may need to adjust the tolerance if the numbering is unusual.

3) Bounding Box - Piles will only be named that are found within a specific area. Create a scope box around the piles you want to name and then select this.

4) Type Marks - The pile type mark is the element parameter the script will search for to find the piles (can't search by "Structural Foundations" as you get everyting, couldn't search by "family" as I have different piles types). Pile cap prefix is the start of the type mark for pile caps. This means that different areas and piles can be distinguised by the type marks in the element type parameters. As an example I had pile caps PC1, PC2, PC3, etc. so the Pile Cap prefix would be PC and other pilecap types, for example, slab piles - SPC, were ignored. Useful for if you have different areas or pile types.
