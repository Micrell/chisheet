## HomeBrew 

Installation :
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## ZSH

Installation : 
```sh
brew install zsh
```

## Oh my Zsh

Installation :
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Configuration :
```sh
vim ~/.zshrc
#Change theme to "fino"
```
	Also add Powerline font to get non ASCII form and set iterm2 to use this font when for non-ASCII char( ,, etc)

## TMUX

Installation :
```sh
brew install tmux
```

No configuration, I prefer took **Oh my Tmux**

## Oh my Tmux

Installation :
```sh
cd
git clone https://github.com/gpakosz/.tmux.git
ln -s -f .tmux/.tmux.conf
cp .tmux/.tmux.conf.local .
```

Configuration :
```sh
vim ~/.tmux.conf.local
#Change regular form to fancy Emoticon
```

## Pyenv

Installation:
```sh
brew install pyenv
```

Configuration:
```sh
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
```

## Tools

- tree : for nagivation, show filesystem as a tree
- nmap : for pentesting, provides port scan cmd 
- samba : for pentesting, provides smbclient cmd
- openvpn : for remote connection, provides cmd for vpn connection
- 