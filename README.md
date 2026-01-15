# tilix-gentoo

Tilix installer script for Gentoo Linux

**tilix-gentoo** provides a simple way to install **Tilix**, a tiling terminal emulator, on **Gentoo Linux**. The goal of this project is to make installing the tilix terminal in a quick and straightforward way without any need for manual setup.

---

## What this does

- Installs Tilix on Gentoo Linux
- Handles required dependencies
- Keeps the installation process simple and transparent

---

## Requirements

- Gentoo Linux
- Git or wget
- Root or sudo access
- Internet connection

---

## Installation

You can install Tilix in one of the following ways.

### Option 1: Automatic install (recommended)

Clone the repository and run the installer script:

```sh
git clone https://github.com/howtoedittv/tilix-gentoo
cd tilix-gentoo
chmod +x get-tilix
./get-tilix
```
### Option 2: Manual installation (advanced)

This option documents the full manual process for installing Tilix on Gentoo without the helper script.

Install required tools and repositories:

```sh
sudo emerge -q dev-vcs/git wget app-eselect/eselect-repository

sudo eselect repository enable dlang
sudo emerge --sync dlang
```

Accept required keywords:

```sh
echo "dev-lang/dmd ~amd64" | sudo tee -a /etc/portage/package.accept_keywords/dmd

echo "app-eselect/eselect-dlang ~amd64" | sudo tee -a /etc/portage/package.accept_keywords/eselect-dlang
```

Install dependencies:

```sh
sudo emerge -q x11-libs/vte:2.91 dmd
```

Install DUB manually:

```sh
cd ~
wget https://github.com/dlang/dub/releases/download/v1.40.0/dub-v1.40.0-linux-x86_64.tar.gz
tar -xvf ~/dub-v1.40.0-linux-x86_64.tar.gz
rm ~/dub-v1.40.0-linux-x86_64.tar.gz
chmod +x ~/dub
sudo mv ~/dub /usr/bin
```

Build and install Tilix:

```sh
cd ~
git clone https://github.com/gnunn1/tilix.git
cd tilix
dub build --build=release
sudo ./install.sh
sudo mv ~/tilix/tilix /usr/bin/
```
---


## Usage

After installation, launch Tilix by running:

```sh
tilix
```
---

## License

MIT License © 2025 barry

