![sxiv](http://muennich.github.com/sxiv/img/logo.png "sxiv")

**Simple X Image Viewer**

This is my fork of sxiv with extra features. Namely:
* a split view mode where you can see thumbnails on the left half of the window and the blown up image of whatever thumbnail you have selected on the right side
* the addition of a "filter" script, that you can call with a keybinding to change the images that sxiv currently displays

If you only want one of these features, you can clone one of the branches instead (the "sim" branch for split view mode, the "filter" branch for the filtering script).

Split-view Mode
--------
Pressing return/enter now cycles through thumbnail mode, split view mode, and image mode.

Filtering script
--------
You may now put a script called "filter" in the same location as "key-handler" (exec/.). 
When you press shift+f, this script will be invoked. The script should print the files that you want to be displayed to stdout, separated by newlines. These files will be displayed, while the files not selected will not be displayed. Any line of the script's stdout that does not match any file that sxiv was originally opened with will be ignored.

Features
--------

* Basic image operations, e.g. zooming, panning, rotating
* Customizable key and mouse button mappings (in *config.h*)
* Thumbnail mode: grid of selectable previews of all images
* Ability to cache thumbnails for fast re-loading
* Basic support for multi-frame images
* Load all frames from GIF files and play GIF animations
* Display image information in status bar


Screenshots
-----------

**Image mode:**

![Image](http://muennich.github.com/sxiv/img/image.png "Image mode")

**Thumbnail mode:**

![Thumb](http://muennich.github.com/sxiv/img/thumb.png "Thumb mode")


Dependencies
------------

sxiv requires the following software to be installed:

  * Imlib2
  * X11
  * Xft
  * freetype2
  * fontconfig
  * giflib (optional, disabled with `HAVE_GIFLIB=0`)
  * libexif (optional, disabled with `HAVE_LIBEXIF=0`)

Please make sure to install the corresponding development packages in case that
you want to build sxiv on a distribution with separate runtime and development
packages (e.g. *-dev on Debian).


Building
--------

sxiv is built using the commands:

    $ make
    # make install

Please note, that the latter one requires root privileges.
By default, sxiv is installed using the prefix "/usr/local", so the full path
of the executable will be "/usr/local/bin/sxiv".

You can install sxiv into a directory of your choice by changing the second
command to:

    # make PREFIX="/your/dir" install

The build-time specific settings of sxiv can be found in the file *config.h*.
Please check and change them, so that they fit your needs.
If the file *config.h* does not already exist, then you have to create it with
the following command:

    $ make config.h


Usage
-----

Please see the [man page](http://muennich.github.com/sxiv/sxiv.1.html) for
information on how to use sxiv.
