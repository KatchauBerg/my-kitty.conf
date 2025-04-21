# my-kitty.conf

Needs Configuration


DEPENDECIAS:

FZF

CONFIG:

INSERT ON .ZSHRC or .BASHRC:

```
  export KITTY_DIR="$HOME/.config/kitty"
  export KITTY_THEMES_DIR="$KITTY_DIR/themes"
  KITTY_CURRENT_THEME="$KITTY_DIR/current-theme.conf"

  if [[ -f "$HOME/.config/kitty/theme-state.txt" ]]; then
    THEME_NAME=$(cat "$HOME/.config/kitty/theme-state.txt")
    kitty @ set-colors -a "$HOME/.config/kitty/themes/${THEME_NAME}.conf"
  fi

  _kitty_themes() {
    local themes=($(fd -e conf --base-directory ~/.config/kitty/themes | sed 's/\.conf$//'))
    COMPREPLY=($(compgen -W "${themes[*]}" -- "${COMP_WORDS[1]}"))
  }
```

DONE, JUST CHANGE YOUR THEMES NOW

SHORTCUT:

CTRL+SHIFT+Y -> CHANGE TERM THEME

remember to comment starship shortcut on last line of program
