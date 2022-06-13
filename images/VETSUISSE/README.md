---
title: Animation of hoof scan
author: David Haberthür
date: 13.06.2022
---

Since `Limb02` was so big that we couldn't scan it with a stacked scan, we acquired two scans at different height (0 mm and 42 mm).
We didn't manage to register the two datasets with DataViewer [1], so we merged the two stacks *with* a filler stack in ImageJ.

42 mm height difference at 40.999924 um corresponds to 1024.392142776 slices, rounded down these are 1024 slices.
We thus made an empty 'filler' stack in ImageJ with a size of 3072 x 3072 x 1024.
We then concatenated rec01+filler and filler+rec02 and used `Process > Image Calculator` to `average` both stacks together.
Since averaging together both stacks with the Image calculator lead to a change in gray value distribution in the overlapping part, we chose a different route.

The 'overlapping' stack is 1941+1024=2965 slices big.
We thus load the bottom 1483 slices from rec_01_00mm_41.0um_AlCu and the top 1483 slices from rec_02_42mm_41.0um_AlCu (All slices from slice 459 on).
We then concatenated both these partial stacks together (` Image › Stacks › Tools  › Concatenate...`) and saved them as `concatenated.tif`.
This merged stack was then 2x binned and saved out as slices in the `merged`folder.

For the visualization we loaded the dataset twice.
One dataset was thresholded to (mostly) only show the blood vessels (with a threshold of 75).
The original and thresholded dataset were then merged with `Image › Color › Merge Channels` and animated with 3DScript.

The animation file is saved to this folder as `Limb02.animation.txt`, the frames as single PNG files



[1]: A 'support request' is hanging with Bruker.
