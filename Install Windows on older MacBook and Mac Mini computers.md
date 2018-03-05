# Install Windows on older MacBook and Mac Mini computers

## Requirements
- Windows install CD/DVD or image
- Windows Assessment and Deployment Kit (Windows ADK)  or 
- Windows Automated Installation Kit (AIK) for Windows 7
- A tool to mount .iso files (something like MagicDisc)

## Procedure
- Install the ADK or the AIK
- Add the folder where oscdimg.exe is located to the %PATH% (so oscdimg.exe can be called from command line)
- Mount the Windows install image or insert the install DVD (let's say it mounts as D:\ drive)
- Create the .iso for the new install disc (`oscdimg -n -m -bd:\boot\etfsboot.com d:\ c:\new_install_disc.iso`)
- Burn **c:\new_install_disc.iso** to a physical disk

## Resources

- Download and install the Windows ADK   
https://docs.microsoft.com/en-us/windows-hardware/get-started/adk-install
   
- Windows Automated Installation Kit (AIK) for Windows 7   
https://www.microsoft.com/en-us/download/details.aspx?id=5753
   
- MagicDisc Download   
http://www.magiciso.com/tutorials/miso-magicdisc-history.htm
   
- Forum: "Stuck at "Select CD-Rom Boot Type""   
https://forums.macrumors.com/threads/help-stuck-at-select-cd-rom-boot-type.467704/
      
- Installing Windows 7 64-Bit on Mac Mini   
https://blogs.msdn.microsoft.com/darrenliu/2011/05/08/installing-windows-7-64-bit-on-mac-mini/
