# Visual Studio Code

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

