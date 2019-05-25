# Add to explorer context (or right click) menu

 - with a text editor, create a .reg file like `subl.reg` and add the code below
 - update paths
 - save
 - then open "Command Prompt" as administrator and run `subl.reg`

#

```reg
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\*\shell\Edit with Sublime Text]
@="Edit with &Sublime Text"
"Icon"="C:\\Program Files\\Sublime Text 3\\sublime_text.exe,0"
"MuiVerb"="Edit with Sublime Text"

[HKEY_CLASSES_ROOT\*\shell\Edit with Sublime Text\command]
@="C:\\Program Files\\Sublime Text 3\\sublime_text.exe \"%1\""

[HKEY_CLASSES_ROOT\Directory\Background\shell\Sublime]
@="Open with Sublime Text"
"Icon"="C:\\Program Files\\Sublime Text 3\\sublime_text.exe,0"

[HKEY_CLASSES_ROOT\Directory\Background\shell\Sublime\command]
@="\"C:\\Program Files\\Sublime Text 3\\sublime_text.exe\" \"%V\""

[HKEY_CLASSES_ROOT\Directory\shell\Sublime]
@="Open with Sublime Text"
"Icon"="C:\\Program Files\\Sublime Text 3\\sublime_text.exe,0"

[HKEY_CLASSES_ROOT\Directory\shell\Sublime\command]
@="\"C:\\Program Files\\Sublime Text 3\\sublime_text.exe\" \"%1\""
```


