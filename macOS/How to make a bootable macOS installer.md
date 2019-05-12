# How to make a bootable macOS installer

 - Plug in an external drive with at least 8GB space (preferably 12GB) as that’s how much the installer will require.
 - Launch Disk Utility (press Cmd + spacebar and start to type Disk Utility).
   - Before this next step - if you are running High Sierra you will need to click on the View drop down below the close minimise buttons.    - Choose Show All Devices from the options. Now you will see the external root drive in addition to the volume below it.
 - Select the root drive in the sidebar (the next step won't with if you only select the volume).
 - Click on Erase.
   - Choose Mac OS Extended (Journaled) as the Format.
   - Choose GUID Partition Map as the Scheme.
     - Your drive will be called Untitled by default, you could give your drive a name such as "macOS" or "USB". (Note you just need to replace the term USB in the Terminal command with the name of your drive).
   - Click on Erase.
 - Wait while Disk Uitlity creates the partition and sets up the drive (this can take a few minutes).
 - Then click Done.
