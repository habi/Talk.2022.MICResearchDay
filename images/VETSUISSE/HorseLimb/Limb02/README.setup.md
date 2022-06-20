---
title: Setup of hoof scan in the machine
author: David Haberthür
date: 14.06.2022
---

We burst the movie `IMG_6950.mov` into frames with`ffmpeg -i IMG_6950.MOV setup-frames/IMG_6950%04d.jpg`.
The frames were then rotated by -4° to have the supports in the 2214 approximately horizontal with
`mogrify -rotate "-4" *.jpg`.
The frames were then cropped to a smaller size with `mogrify -crop 940x1400+140+70 *.jpg`, based on the bottom of bottom of https://web.archive.org/web/20190716161718/https://lib.bsu.edu/wiki/index.php?title=ImageMagick
