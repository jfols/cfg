## install brew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## git
```
brew install git
```

## rust
install --> [rustup.rs](https://rustup.rs/)

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## n

```
brew install n
n install current
n install lts
n use lts
```

add to .zshrc
```
export N_PREFIX=~/n
```

## oh-my-zsh
```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## powerlevel10k
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
set `ZSH_THEME="powerlevel10k" in `~/.zshrc`
## install alacritty from source

`brew install alacritty`

or...

### for M1
https://bou.ke/blog/macbouk-air/

clone alacritty repo, inside repo:

```
rustup target add x86_64-apple-darwin aarch64-apple-darwin;

cargo build --release --target=x86_64-apple-darwin;

cargo build --release --target=aarch64-apple-darwin;

lipo target/{x86_64,aarch64}-apple-darwin/release/alacritty -create -output alacritty;
```

## automator application for alacritty

- run script:
```
nohup /Applications/build/alacritty > /dev/null 2>&1 &
```
- save as application "Alacritty"

## set alacritty icon

- copy alacritty png from finder cmd+a, cmd+c
- open file info for alacritty (cmd+i), select icon in top left, cmd-v

## configure alacritty
add default `.config/alacritty/alacritty.yml` from https://github.com/alacritty/alacritty/releases

uncomment what ya like

## tmux
```
brew install tmux
```

learn tmux
https://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/

customize tmux
https://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/

### install tpm

https://github.com/tmux-plugins/tpm

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

draculat theme --> https://draculatheme.com/tmux

set -g @plugin 'dracula/tmux'  


## let's put this config into a git repo (hey it's this one!)

```
git init --bare $HOME/.cfg
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
config config --local status.showUntrackedFiles no
echo "alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'" >> $HOME/.zshrc
```

To add/update config files

```
config add .zshrc
config add .tmux.conf
config add .config
```