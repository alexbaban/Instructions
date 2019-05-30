# How to show the stored WiFi password

 - open terminal as administrator
 - run `netsh`
 - run `wlan show profile` to list saved profiles
 - run `wlan show profile <profile name> key=clear` (password is under "key content")
 
