# Pop!OS backup and setup

either for setting up new computers or for backing up/syncing setup between existing computers.

## custom applications (/usr/share/applications)

```bash
# backup
copy scripts to gist

# restore
curl "https://gist.githubusercontent.com/alifeee/bb0499e1272f312b82497031d28e91f2/raw/59195448f2edb8ce8f02ef8ca5954af628c3a112/clone.sh" > ~/Desktop/clone.sh
curl "https://gist.githubusercontent.com/alifeee/bb0499e1272f312b82497031d28e91f2/raw/59195448f2edb8ce8f02ef8ca5954af628c3a112/clone.desktop" > /usr/share/applications/clone.desktop
```

## nautilus scripts

```
# backup
cp -r ~/.local/share/nautilus/scripts nautilus/scripts
git ...

# restore
mkdir -p ~/.local/share/nautilus/scripts
cp -r nautilus/scripts ~/.local/share/nautilus/scripts
```

## `.bashrc`

```
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

