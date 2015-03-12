xmonad-wallpaperhook
====================

**This is now in xmonad-contrib-darcs! If you just want to install it, get it there!**

This is my log hook for xmonad to set different wallpapers for each workspace.

The runtime dependencies are imagemagick and feh (the CLI tools should be installed).
They are used to first combine the wallpapers on the virtual xinerama screen and then
set the merged wallpaper onto the virtual canvas, making the correct wallpaper appear
on the according workspace.

The reason for this workaround is that I wanted the images be automatically aligned
with the screen orientation - horizontal pictures on vertical screens or vertical
pictures on horizontal screens will be rotated by 90 degrees.

As xmonad workspaces are independent from physical screens, there is no way to know
a priori which pictures are to be rotated, so the only alternative would be to pre-render
and save a rotated copy for all of them. I decided against duplicating all wallpapers
on my hard drive and to use real-time orientation.

Mainly because the conversion and merging takes some time, expect the wallpapers to have
a lag of 0.5s following the workspace changes.

If you come up with some hack to speed this up, a pull request is appreciated.

This is my first xmonad extension and the code is rather ugly as I don't know better,
so I also appreciate refactoring of this code or some tips. In the current condition I
won't even try to submit this to the official xmonad-contrib package.

Look at the haddock documentation to see how to integrate it into your xmonad.hs.
