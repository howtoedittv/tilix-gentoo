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

### Option 1: Clone the repository

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

