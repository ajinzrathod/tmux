You can enable this as a default setting in .tmux.conf with the following:

```
set-window-option -g mode-keys vi`
```

You can confirm this is working by pressing Ctrl+B and then : in a tmux session to bring up the command line, and typing:

```
list-keys -T copy-mode-vi
```

-----

You use space bar for the beginning of the selection and enter for the end.

**copy:**

   - <kbd>Ctrl</kbd><kbd>b</kbd> <kbd>[</kbd>
   - <kbd>Space</kbd>
   - <kbd>Enter</kbd>

**paste:**
  - <kbd>Ctrl</kbd><kbd>b</kbd> <kbd>]</kbd>

**OR**

If you don’t mind artifically introducing a few Vim-only features to the vi mode, you can set things up so that v starts a selection and y finishes it in the same way that Space and Enter do, more like Vim:

```
bind-key -T copy-mode-vi 'v' send -X begin-selection
bind-key -T copy-mode-vi 'y' send -X copy-selection-and-cancel
```
-----
