# Pile_Naming
Dynamo Script for producing unique names for piles within Revit

---

This script was created to automate pile naming within Revit. When run, this script will search for piles within a model, determine which piles are part of the same pile cap and provide unique names for each pile. The script was created in order to automate the naming process when creating piles schules. Piles will be named from the top left to the bottom right.

The current script is not amazingly efficient as it works in a exponential way, so it is advised to name piles in groups or strips. The naming can be split using a scope box to limit the number of piles named at any one time.

The families themselves have a pile family within a pile cap family. It may be possible to alter the families to name piles within a pilecap and then just name the pilecap (which would make this script a lot faster) but this script was written to use families that had already been produced and the user did not want to change. 

---

# Controls

There are a number of options within the script that will help to organise and limit the number of piles that are named

a.	Categories – Always set to Structural Foundations, it's only there as in the past it has accidentally changed between models.

b.	Pile Naming Prefix – This is what you want to start the pile names with. E.g. SP for slab piles, PC for pile cap piles

c.	Start Number – The number the pile naming will start with. Useful when naming piles in chunks

d.	Bounding box – Place a scope box around the piles you want to name and select it. Only piles within the bounding box will be named

e.	X and y tolerance – This just helps to normalise the naming a little. If a pile cap is a couple of mm off from an adjacent pile cap then it will ignore this difference and keep the naming going from left to right, rather than skipping it and coming back for it on the next pass. I usually keep to 500 but try and change if you get some funny numbers

f.	Type Marks – The script will look for elements that already have these type marks in their element type.

>i.	All piles within the pile cap family should have the same type mark. At the moment this is FP.

>ii.	The pile cap type mark helps to group the piles that you want to name. Each pile cap element type should have a specific tpye mark. I used SPC for any slab piles I was naming or PC for pile caps. (It says prefix because different pile caps were named PC1, PC2 etc. depending on the number of piles. Don’t put in the number, you’ll break it!) It is useful to create new element types for different areas so they can be split out. The scope box will help do this but might not be perfect when foundations are right next to the building or if the building is a funny shape.

