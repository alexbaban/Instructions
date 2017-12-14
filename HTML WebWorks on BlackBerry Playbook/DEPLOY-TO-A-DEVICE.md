# Deploy to a device

## Before you begin

Make sure that your BlackBerry PlayBook tablet is on the same network as your computer.

Make sure that your BlackBerry PlayBook tablet is in `Development Mode`.

## Create a debug token

At a command prompt, navigate to blackberry-tablet-sdk\bin in your BlackBerry PlayBook OS SDK folder.

Create a debug token for your device by using the following syntax and values for the command line options

`blackberry-debugtokenrequest -storepass <KeystorePassword> 
    -devicepin <device PIN> <debug_token_file_name.bar>`
