# mydebian

## install driver files (7800xt)

go to https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/

download latest firmware package.

copy everything that's in the amdgpu dir to /lib/firmware/amdgpu

## window tiling (bismuth)

```bash
sudo apt install kwin-bismuth
```

## KDE theming

### wallpaper

```bash
wget https://github.com/teacher-svb/mydebian/raw/refs/heads/main/wallpapers/no-mans-sky-minimal-art_3840x2160.jpg -P ~/.local/share/wallpapers/
```

### launcher (onzeMenu)

```bash
cd ~/Downloads && wget https://github.com/teacher-svb/mydebian/raw/refs/heads/main/launcher/OnzeMenu.tar.gz -P ~/Downloads/ && plasmapkg2 -i ./OnzeMenu.tar.gz
```

### cursors

we10xos

### dolphin changes

### Task Switcher (alt-tab behaviour)

settings > window management > task switcher > get new task switchers... > thumbnail switcher

### shortcuts

https://github.com/teacher-svb/mydebian/raw/refs/heads/main/shortcuts/shortcuts.kksrc

settings > shortcuts > shortcuts > import schema

## NerdFont installation

```bash
wget -P ~/.local/share/fonts https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/JetBrainsMono.zip \
&& cd ~/.local/share/fonts \
&& unzip JetBrainsMono.zip \
&& rm JetBrainsMono.zip \
&& fc-cache -fv
```

## FastFetch

https://github.com/fastfetch-cli/fastfetch/releases

fastfetch --gen-config

overwrite fastfetch config with the one from https://github.com/teacher-svb/mybash/raw/refs/heads/main/fastfetch/config.jsonc

## myBash (via mybash repo)

```bash
mkdir -p ~/build
cd ~/build
git clone https://github.com/teacher-svb/mybash
```

```bash
cd ~/build/mybash
./setup.sh
```

## docker installation

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## docker desktop installation

https://docs.docker.com/desktop/install/linux/debian/

## Github CLI

```bash
(type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

```bash
gh auth login
```
