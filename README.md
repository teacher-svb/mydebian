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

### dolphin changes



### shortcuts

https://github.com/teacher-svb/mydebian/raw/refs/heads/main/shortcuts/shortcuts.kksrc

settings > shortcuts > shortcuts > import schema

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

```
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

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## docker desktop installation

https://docs.docker.com/desktop/install/linux/debian/
