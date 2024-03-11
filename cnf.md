## Powershell

Installation de chacolatey :

```bash
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

Installation des fonts :

```bash
choco install nerd-fonts-hack
```

## WSL

Afficher les version WSL :

```powershell
wsl.exe -l -v
```

Supprimer les distributions installées :

```powershell
wsl --unregister <distro>
```

Définir la version, par défaut :

```powershell
wsl --set-default-version 2
```

Lister les distributions disponibles :

```powershell
wsl --list --online
```

Installer la distribution souhaité :

```powershell
wsl --install -d Ubuntu-22.04
```

Définir la distribution comme distribution par défaut :

```powershell
wsl --set-default Ubuntu-22.04
```

## Linux

Connexion au compte root :

```bash
sudo -i
```

Configuration des permissions de l'utilisateur :

```bash
echo -e "nbecu   ALL=(ALL:ALL) NOPASSWD: ALL" > /etc/sudoers.d/nbecu
```

Mise à jour du système :

```bash
apt update && sudo apt upgrade
```

Installation des paquets nécessaires :

```bash
apt install -y \
    git \
    tmux \
    vim \
    zsh \
    wget \
    curl
```

Déconnexion du compte root :

```bash
exit
```

Installation de Oh My ZSH:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Installation de powerlevel10k :

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

Installation de l'auto-suggestion :

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Installation de la mise en valeur des synthaxes :

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Edition du thème :

```bash
sed -i 's/^ZSH_THEME.*/ZSH_THEME="powerlevel10k\/powerlevel10k"/' ~/.zshrc
```

Edition des plugins :

```bash
sed -i 's/^plugins.*/plugins=(git zsh-syntax-highlighting zsh-autosuggestions)/' ~/.zshrc
```

Application des modifications :

> Le fichier `.p10k.zsh` doit être copié initialement à la racine du home

```bash
source ~/.zshrc
```

## Docker

Installation depuis ce lien : https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe