#PLAYSTATION(3)Conteroller OS X Fix

Based on comment by [@MrRocketman](https://github.com/OpenEmu/OpenEmu/issues/1041#issuecomment-39808894).
***
YES!! I got the Chinese controllers working over Bluetooth with Mavericks!

### Follow these steps exactly to get your Chinese controller working.

The problem was with Mavericks' caching the plist. So the key is to load your changes into Mavericks' cache. Big thanks to Clobber for pointing me in the right direction.

A screenshot of the file you are about to edit  
![screen shot 2014-05-12 at 5 28 43 pm](https://cloud.githubusercontent.com/assets/1709766/2951763/393325ea-da2d-11e3-8ef2-797b3ccc9368.png)

So the steps are:

*   Turn on bluetooth on your mac in System Preferences (If it isn’t already)
*   Connect the controller via USB
*   Press the P3 button on the controller
*   Disconnect the USB  
    (The controller will now show up in System Preferences->Bluetooth. Remember what the name of the device shows up as. You will need it in a minute. It will say it's 'connected', but will say 'disconnected' after about 20 seconds. It is not yet functioning at this point)
*   Drag the file from /Library/Preferences/com.apple.Bluetooth.plist to your desktop
*   Open the copy that is on your desktop with Xcode (Download Xcode from the App Store if you don't have it)
*   Click the triangle next to 'DeviceCache' to expand it  
    ![screen shot 2014-05-12 at 5 44 13 pm](https://cloud.githubusercontent.com/assets/1709766/2951890/bb548d14-da2f-11e3-8831-a7c466962fa9.png)
*   Click on the triangles of the expanded items until you find the one that is `Name String PLAYSTATION(R)3Conteroller` (See the picture above)
*   Now add a new item with the '+’ button (find the ‘+’ button by clicking on one of the items that is expanded), type in 'Services', set the type to 'Data', and paste this massive string `<040b7374 7265616d 74797065 6481e803 84014084 8484074e 53417272 61790084 84084e53 4f626a65 63740085 84016902 92848484 1b494f42 6c756574 6f6f7468 53445053 65727669 63655265 636f7264 00949284 84841149 4f426c75 65746f6f 74684465 76696365 00848411 494f426c 7565746f 6f74684f 626a6563 74009492 84848406 4e534461 74610094 95068404 5b36635d 34c7311b 2be78686 92848484 0c4e5344 69637469 6f6e6172 79009495 18928484 84084e53 4e756d62 65720084 84074e53 56616c75 65009484 012a8495 95008692 84848419 494f426c 7565746f 6f746853 44504461 7461456c 656d656e 74009484 014301a0 0284014c 0492849f 9e848401 71a28200 00010086 8692849f 9ea19581 0a028692 84a3a005 a000a101 92849f9e 84840173 a3018686 92849f9e a1958107 02869284 a3a006a0 05a10892 8484840e 4e534d75 7461626c 65417272 61790093 95019284 a3a006a0 05a10692 84ad9502 9284a3a0 01a001a1 0292849f 9ea19581 09048686 9284a3a0 01a001a1 0292849f 9ea19581 00018686 86868686 92849f9e a1958104 02869284 a3a005a0 00a10192 a8869284 9f9ea195 0d869284 a3a006a0 05a10f92 84ad9501 9284a3a0 06a005a1 0d9284ad 95029284 a3a006a0 05a10692 84ad9502 9284a3a0 03a001a1 02928484 8412494f 426c7565 746f6f74 68534450 55554944 009b9284 9b950284 045b3263 5d010086 86869284 a3a001a0 01a10292 849f9ea1 95138686 86869284 a3a006a0 05a10392 84ad9501 9284a3a0 03a001a1 029284bf 92849b95 02a60011 86868686 86868686 8692849f 9ea19581 0c028692 84a3a001 a001a102 92849f9e a1958180 3e868692 849f9ea1 95810102 869284a3 a001a001 a10292b3 8692b392 84a3a004 a005a113 92849b95 1384055b 3139635d 57697265 6c657373 20436f6e 74726f6c 6c657286 8692849f 9ea19581 09028692 84a3a005 a000a101 92a88692 849f9ea1 95810602 869284a3 a006a005 a1819a00 9284ad95 019284a3 a006a005 a1819800 9284ad95 029284a3 a001a000 a1019284 9f9ea9a3 22868692 84a3a004 a005a181 94009284 9b958194 0084065b 31343863 5d050109 04a101a1 02850175 08950115 0026ff00 81037501 95131500 25013500 45010509 19012913 81027501 950d0600 ff810315 0026ff00 05010901 a1007508 95043500 46ff0009 30093109 32093581 02c00501 75089527 09018102 75089530 09019102 75089530 0901b102 c0a10285 02750895 300901b1 02c0a102 85ee7508 95300901 b102c0a1 0285ef75 08953009 01b102c0 c0868686 86868692 849f9ea1 95048692 84a3a006 a005a10d 9284ad95 029284a3 a006a005 a1069284 ad950292 84a3a003 a001a102 9284bf92 849b9502 a6010086 86869284 a3a001a0 01a10292 849f9ea1 95118686 86869284 a3a006a0 05a10392 84ad9501 9284a3a0 03a001a1 029284bf 92849b95 02a60011 86868686 86868692 849f9ea1 95810e02 869284a3 a005a000 a1019284 9f9ea9a3 00868692 849f9ea1 95810302 869284a3 a001a000 a1019284 9f9ea9a3 21868692 849f9ea1 95810201 869284a3 a004a005 a11b9284 9b951b84 055b3237 635d536f 6e792043 6f6d7075 74657220 456e7465 72746169 6e6d656e 74868692 849f9ea1 95018692 84a3a006 a005a103 9284ad95 019284a3 a003a001 a1029284 bf92849b 9502a611 24868686 86869284 9f9ea195 810b0286 9284a3a0 01a001a1 0292b386 92849f9e a1958100 02869284 a3a001a0 01a10292 b3869284 9f9ea195 09869284 a3a006a0 05a10892 84ad9501 9284a3a0 06a005a1 069284ad 95029284 a3a003a0 01a10292 84bf9284 9b9502a6 11248686 869284a3 a001a001 a10292b3 86868686 8692849f 9ea19581 08028692 84a3a005 a000a101 92eb8692 849f9ea1 95068692 84a3a006 a005a109 9284ad95 039284a3 a001a001 a1029284 9f9ea195 816e6586 869284a3 a001a001 a1029284 9f9ea195 6a868692 84a3a001 a001a102 92b38686 8692849f 9ea19581 05028692 84a3a005 a000a101 92a88692 849f9ea1 95810d02 869284a3 a005a000 a10192eb 8692849f 9ea19581 02028692 84a3a001 a000a101 92eb8692 849f9ea1 95810101 869284a3 a004a005 a1139284 9b9513a7 57697265 6c657373 20436f6e 74726f6c 6c657286 86868692 84969297 92849d95 0c929e92 84a3a001 a002a104 92849f9e a5a28201 00010086 86921592 84a3a004 a005a11a 92849b95 1a84055b 3236635d 504c4159 53544154 494f4e28 52293320 436f6e74 726f6c6c 65728686 920f9284 a3a001a0 01a10292 849f9ea1 95028686 92fc9284 a3a006a0 05a10892 84ad9501 9284a3a0 06a005a1 069284ad 95029284 a3a003a0 01a10292 84bf9284 9b9502a6 12008686 869284a3 a001a001 a10292b3 86868686 8692cb92 84a3a001 a001a102 92849f9e a195814c 05868692 ec9284a3 a001a001 a10292b3 8692f292 84a3a006 a005a103 9284ad95 019284a3 a003a001 a1029284 bf92849b 9502a612 00868686 868692b4 9284a3a0 05a000a1 0192a886 92139284 a3a001a0 01a10292 849f9ea1 95816802 868692fa 9284a3a0 01a001a1 0292b386 92079284 a3a006a0 05a10992 84ad9503 9284a3a0 01a001a1 02920b86 9284a3a0 01a001a1 02920d86 9284a3a0 01a001a1 0292b386 868692da 9284a3a0 06a005a1 0d9284ad 95029284 a3a006a0 05a10692 84ad9502 9284a3a0 03a001a1 029284bf 92849b95 02a60100 86868692 84a3a001 a001a102 92f28686 869284a3 a006a005 a1039284 ad950192 84a3a003 a001a102 9284bf92 849b9502 a6000186 86868686 86868686 86>`
*   Now find the item 'ClassOfDevice' and change the number to 1,288
*   Now add another item and name it 'LastServiceUpdate', set the type to 'Date', and hit tab to set the default time  
    [![screen shot 2014-05-12 at 5 28 43 pm copy](https://cloud.githubusercontent.com/assets/1709766/2951891/c4d6befc-da2f-11e3-83fa-cc52ce2249dc.png)](https://cloud.githubusercontent.com/assets/1709766/2951891/c4d6befc-da2f-11e3-83fa-cc52ce2249dc.png)
*   Save the file
*   Now turn off Bluetooth in System Preferences
*   Quit System Preferences
*   Drag the com.apple.Bluetooth.plist file from your Desktop back to /Library/Preferences to overwrite the file there (Click authenticate. Click replace. Then type in your password. )

THE MOST IMPORTANT STEPS FOR MAVERICKS:

*   Open up the 'Terminal' app and paste in the following: `defaults read /Library/Preferences/com.apple.Bluetooth.plist` Hit enter to execute this command.  
    (This causes Mavericks to load in the file you just edited into it's cache.)
*   Logout of your computer, then log back in
*   Now turn Bluetooth back on in System Preferences if it isn’t already
*   Push the 'P3' button on your controller to connect and you are good to go! (Besides choosing the controller in OpenEmu's preferences of course)

The key thing here is that the Services that you pasted into the bluetooth.plist need to still be there after you turn Bluetooth back on. Once you've got that to work after logging out and back in you should be golden.

