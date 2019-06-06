# Settings

## Disable crash reporting
 - From "File" > "Preferences" > "Settings" search for `telemetry`  
(https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-crash-reporting)

## Enable "format on save" for JavaScript code
 - Click on "File" > "Preferences" > "Settings"
 - Click on "Open Settings (JSON)" icon `{}` at top right
 - Add the code below to the settings object
```json
    "[javascript]": {
        "editor.formatOnSave": true
    }
```
