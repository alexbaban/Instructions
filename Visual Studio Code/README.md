# Visual Studio Code

## Creating your own snippets
Code snippets are templates that make it easier to enter repeating code patterns, such as loops or conditional-statements.
 - https://code.visualstudio.com/docs/editor/userdefinedsnippets

## Portable Mode

Portable mode is supported on the ZIP download for Windows and Linux, as well as the regular Application download for macOS.

After unzipping the VS Code download, simply create a `data` folder within Code's folder (at the same level with `Code.exe`).

Also, create an empty `tmp` directory inside the data folder, it will be used for TMP data.

(https://code.visualstudio.com/docs/editor/portable)

## Add key bindings to transform selected text to upper/lower case

Make <kbd>ctrl+k ctrl+u</kbd> and <kbd>ctrl+l ctrl+l</kbd> work (just like in Sublime Text)

* Open "Keyboard Shortcuts" with <kbd>ctrl+k ctrl+s</kbd>
* Open "keybindings.json"
* Add this:

```json
[
    {
        "key": "ctrl+k ctrl+u",
        "command": "editor.action.transformToUppercase",
        "when": "editorTextFocus"
    },
    {
        "key": "ctrl+k ctrl+l",
        "command": "editor.action.transformToLowercase",
        "when": "editorTextFocus"
    }
]
```

* save and close "keybindings.json"

