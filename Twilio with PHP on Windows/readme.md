# Twilio with PHP on Windows

## Download and install MAMP
(https://www.mamp.info/en/)

* default install folder `C:\MAMP\`
* default website root folder `C:\MAMP\htdocs\`

## Create `info.php` and save to website root

``` php
<?php

// Show all information, defaults to INFO_ALL
phpinfo();

// Show just the module information.
// phpinfo(8) yields identical results.
phpinfo(INFO_MODULES);

?>

```

### load `http://localhost/info.php` in browser

* check for `Loaded Configuration File`, for example	`C:\MAMP\conf\php7.2.1\php.ini`
* check for `cURL support`, should be set to `enabled`

## Download `The Twilio PHP SDK`
(https://www.twilio.com/docs/libraries/php)   
(https://github.com/twilio/twilio-php)   

* unzip and copy `Twilio` folder to webroot (`C:\MAMP\htdocs\`)

## Create `twilio.php` file and save to website root

``` php
<?php

require __DIR__ . '/Twilio/autoload.php';

use Twilio\Rest\Client;

$sid    = "[account or subaccount sid]";
$token  = "[account or subaccount token]";

$twilio = new Client($sid, $token);

$calls = $twilio -> calls -> read(array("startTime" => new \DateTime('2018-6-4')));

foreach($calls as $record) {
    print($record -> sid);
    printf("<br />");

}

?>

```

* load `http://localhost/twilio.php` in browser (this will fail)

## Download and save the necessary CA certs
(https://curl.haxx.se/ca/cacert.pem)
* save to `C:\MAMP\bin\php\`

## Edit `C:\MAMP\conf\php7.2.1\php.ini`
* `display_errors = on`
* `curl.cainfo = "C:\MAMP\bin\php\cacert.pem"`
### restart Apache (or MAMP "Servers")

* load `http://localhost/twilio.php` in browser (should work now)



