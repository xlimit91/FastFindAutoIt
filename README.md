Introduction:
FastFind is an advanced pixel search library for AutoIt scripts. It replaces and improves upon the functionality of the standard AutoIt pixel search functions, PixelGetColor and PixelSearch, allowing for more complex searches to be performed at much faster speeds.
It consists of a .dll file that contains the pixel searching logic, and an AutoIt wrapper file, which acts as an interface between your AutoIt script and the DLL. To start using FastFind, simply copy the files into the same folder as your script, and insert #include "FastFind.au3" near the top of your script file. You will then be able to reference the FastFind functions listed in this help file.

Required Files:
FastFind.au3 AutoIt wrapper (include) 
FastFind.dll Library for 32bit systems 
FastFind64.dll Library for 64bit systems 

How FastFind Works:
One of the reasons FastFind is so much quicker than AutoIt's native pixel search functions is it's use of SnapShots. A SnapShot is basically a pixel map of a specified area on screen as it looked at the time the SnapShot was taken. This pixel information is stored in active memory, which means your script can access it much, much faster than the time it would take to make a new pixel request from the screen. Once a SnapShot is taken, search operations can be performed on that SnapShot until that memory is freed or overwritten.
It is possible to retain up to 1024 different SnapShots simultaneously, but storing an 800x600 SnapShot will divert about 1.8MB of available RAM, so the size and quantity of SnapShots in use at any given time should be kept to a minimum.
FastFind pixel search functions will automatically take a new SnapShot and store it in the default 'slot' when they are called, unless you specify otherwise in the function parameters. This will cause a previous SnapShot to be overwritten if it is also stored in the default 'slot'. Check the individual function help pages for more details and instructions on how to change this behavior.
More advanced operations can be performed with the pixel search functions by maintaining a list of colors and exclusion zones.

FastFrench (antispam@laposte.net): Author of FastFind
Some parts and concept come from Chris Mallett (support@autohotkey.com), modified by kangkengkingkong@hotmail.com
CeramicWeasel : Help file in English for version 1.8 (FastFind.chm)
Frank10 : Update 1.8.4 => 2.0 Autoit Wrapper
AutoIt forum : http://www.autoitscript.com/forum/topic/126430-advanced-pixel-search-library/

 - [v1.4] : find the "best spot" - meaning the spot that has the best number of "right" colors.
 - [v1.4] : now provided with a tool, FFShowPixels.exe, to find colors, manage color lists, show all occurences of them on the Captured Window, and... automatically generates AutoIt or C++ code.
 - [v1.6] : Saves SnapShots on BitMaps (BMP and JPG supported)
 - [v1.6] : Modifies SnapShots with "filters" (Keep only some colors or only pixels that have changes. All other pixels can be turned to black).
 - [v1.7] : Can change pixels colors on SnapShots (SetPixel)
 - [v1.7] : Can access the Raw pixel data of SnapShots (GetRawData)
 - [v1.7] : Can draw back SnapShots on Screen.
 - [v1.8] : Bug fixes. Deleted
 - [v1.8.1] : Bug fixes (FastFind.au3).
 - [v1.8.2] : Bug fixes (FastFind.au3).
 - [v1.8.3] : Bug fixes (FastFind.au3). Deleted
 - [v1.8.4] : Should now run on early XP and Windows 2000 OS.
 - [v2.0] : Documentation file in english (FastFind.chm), several new functions and new feature on some old functions.
 - [v2.1] : Bug fixes (errors in message boxes).
 - [v2.2] : Crashes + error messages (not gone in 2.1 ?!).
