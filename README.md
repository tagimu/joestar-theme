# ★ Joestar Theme
**JJBA** inspired [Starship](https://starship.rs/) prompt and color theme for [Windows Terminal](https://github.com/microsoft/terminal), [iTerm](https://iterm2.com/index.html), **Terminal.app** and [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting).

![Screenshot 1](./screenshot1.png)
![Screenshot 2](./screenshot2.png)

## Prompt Installation
### Starship
First of all you need to install [Starship](https://starship.rs/). Starship is fast and easy customizible cross-shell prompt. Installation is simple, just look for the instructions on the main page.

### Icons 
Use [Nerd Font](https://www.nerdfonts.com/). Every font there has icons embedded. I prefer and also use [FiraCode](https://github.com/tonsky/FiraCode) for Joestar theme. In your terminal you should set this font manualy.

### Add Prompt
> For the Terminal.app you need to use `terminal-app/*-starship.toml` files!

There are two configurations of prompt: with **OS icon** and with **golden star icon** (see screenshots above).

Copy content of the `prompt/*-starship.toml` from this repository into your `~/.config/starship.toml` on Linux/MacOS, or `/Users/{user}/.config/starship.toml` on Windows (or whenever your `$HOME` variable points).

Add init script to your shell config as it says in Starship [install guide](https://starship.rs/#powershell).

## Color Theme
### Windows Terminal
In your Windows Terminal open Settings and click "*Open json*" to open `settings.json`. Past the content of the `windows-terminal/joestar-windows-terminal.json` into `schemes` section and save changes. Now you can activate `Joestar` bizzare colors in the Terminal settings!

### iTerm
Download `iterm/joestar.itermcolors`. Open iTerm2 Preferences -> Profiles. Go to Colors tab and look in selector `Color presets`. Import `joestar.itermcolors`... Nice :)

### Terminal.app
Terminal.app doesn't support rgb colors and works in `xterm-256color` colors range. That's why for the terminal there are it's own files in the `terminal-app` folder.

Download `terminal-app/Joestar.terminal`. Go to Settings -> profiles. Click on the `...` button and choose "*Import*". Add `Joestar.terminal`. Don't forget to click "*Default*" to apply theme.

- Due the fact that Terminal.app uses `xterm-256color` scheme, use `terminal-app/*starship.toml` as config for Starship prompt!
- Same for the `zsh-syntax-highlighting`. You should use `terminal-app/joestar-zsh-syntax-highlighting.zsh` because of the colors.

### Zsh-syntax-highlighting
> For the Terminal.app use `terminal-app/joestar-zsh-syntax-highlighting.zsh`!

If you wnat to hilight syntax in Zsh you may use [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting). It works fine with [Oh My Zsh](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh) either.

Copy content of the `joestar-zsh-syntax-highlighting.zsh` into your `~/.zshrc` before zsh-syntax-highlighting initialization. Update zsh:
```zsh
source ~/.zshrc
```
Done!

## Common problems
### Powershell
It happens sometimes that Powershell doesn't start prompt because of `$PROFILE` execution policy. Next commands may help you:
```pwsh
# Creates Powershell config file if it's not exists
# and adds starship initialization
Add-Content -Path $PROFILE -Value 'Invoke-Expression (&starship init powershell)'

Set-ExecutionPolicy RemoteSigned -Force
```

### That's it!
![JJBA](./jjba.jpg)