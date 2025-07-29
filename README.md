# Pop!_OS backup and setup

either for setting up new computers or for backing up/syncing setup between existing computers.

## custom applications (/usr/share/applications)

```bash
# backup
# copy scripts to gist

# restore
# copy gist 1 (https://gist.github.com/alifeee/bb0499e1272f312b82497031d28e91f2) to scripts
# copy gist 2 (https://gist.github.com/alifeee/c3bf377a2701a62c3f103e908ad83ea8) to scripts

open ~/Desktop/clone.sh
open /usr/share/applications/clone.desktop
open /usr/bin/upload-file.sh
open /usr/share/applications/upload-file.desktop
```

## nautilus scripts

```bash
# backup
cp -r ~/.local/share/nautilus/scripts/ nautilus/scripts
git ...

# restore
mkdir -p ~/.local/share/nautilus/scripts
cp -r nautilus/scripts/. ~/.local/share/nautilus/scripts
```

## `.bashrc`

```bash
# backup
cp ~/.bashrc .bashrc

# restore
cp .bashrc ~/.bashrc
```

## gnome extensions

```bash
# see local extensions
firefox https://extensions.gnome.org/local/

# backup
# install https://github.com/oae/gnome-shell-extensions-sync
# set local file to gnome-extensions.txt
# click upload

# restore
# install https://github.com/oae/gnome-shell-extensions-sync
# set local file to gnome-extensions.txt
# click download

# compare
# cat files (after jq) to /tmp/backup and /tmp/current, then:
git diff --no-index --word-diff=color --word-diff-regex="[^ \n\"=:']*" /tmp/backup /tmp/current
```

## gnome settings

```bash
# backup
dconf dump /org/gnome/ > gnome-settings.txt

# restore
dconf load /org/gnome/ < gnome-settings.txt
```

## install atuin

```bash
# backup
# N/A

# restore
# from https://atuin.sh/
curl --proto '=https' --tlsv1.2 -LsSf https://setup.atuin.sh | sh
atuin login
atuin sync
# change atuin command in .bashrc to --disable-up-arrow
echo -e '[dotfiles]\nenabled = true' >> ~/.config/atuin/config.toml
```

## install syncthing

```bash
# probably this, then add folders
sudo apt install syncthing
```
