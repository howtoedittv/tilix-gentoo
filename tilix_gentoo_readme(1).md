# tilix-gentoo

Tilix installer script for Gentoo Linux

**tilix-gentoo** provides a simple way to install **Tilix**, a tiling terminal emulator, on **Gentoo Linux**. The goal of this project is to make installing Tilix quick and straightforward without manual setup.

The repository contains a single file:

- `get-tilix`

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

### Option 2: Download the script directly

Download the script, move it to your home directory, make it executable, and run it:

```sh
wget https://github.com/howtoedittv/tilix-gentoo/releases/download/release/get-tilix
mv get-tilix ~
cd ~
chmod +x get-tilix
./get-tilix
```

### Option 3: Manual installation (advanced)

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
sudo mv ~/dub /usr/bin
sudo chmod +x /usr/bin/dub
```

Build and install Tilix:

```sh
cd ~
git clone https://github.com/gnunn1/tilix.git
cd tilix
dub build --build=release
sleep 3
sudo ./install.sh
sleep 5
sudo mv ~/tilix/tilix /usr/bin/
```

After installation, you should be able to run Tilix by typing:

```sh
tilix
```

---


## Usage

After installation, launch Tilix by running:

```sh
tilix
```

You can also set Tilix as your default terminal in your desktop environment if desired.

---

## Supported Systems

- Gentoo Linux only

---

## Purpose

tilix-gentoo exists to provide a fast and repeatable way to install Tilix on Gentoo Linux.

---

## License

MIT License © 2025 barry

