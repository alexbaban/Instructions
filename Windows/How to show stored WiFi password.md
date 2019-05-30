# How to show the stored WiFi password

 - open a terminal as administrator
 - run `netsh`
 - run `wlan show profiles` to list saved profiles
 - run `wlan show profiles <profile name> key=clear` (password is under "Key Content")
 
