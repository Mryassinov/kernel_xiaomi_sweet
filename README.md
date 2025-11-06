# Kernel for Xiaomi Redmi Note 10 Pro (sweet)

Custom kernel based on Linux 4.14.356 with KernelSU-Next integration.

## Features
- KernelSU-Next support
- Optimized for Xiaomi sweet (Redmi Note 10 Pro)
- Based on sixteen-ksu-next branch

## Supported Devices
- sweet (Redmi Note 10 Pro)
- sweetin (Redmi Note 10 Pro India)

## Building

### Prerequisites
```bash
sudo apt-get install -y bc bison build-essential ccache curl flex \
    g++-multilib gcc-multilib git gnupg gperf imagemagick lib32ncurses5-dev \
    lib32readline-dev lib32z1-dev liblz4-tool libncurses5 libncurses5-dev \
    libsdl1.2-dev libssl-dev libxml2 libxml2-utils lzop pngcrush rsync \
    schedtool squashfs-tools xsltproc zip zlib1g-dev libelf-dev
```

### Setup Toolchain
```bash
mkdir -p $HOME/evo16/prebuilts/clang/host/linux-x86/
cd $HOME/evo16/prebuilts/clang/host/linux-x86/
wget https://android.googlesource.com/platform/prebuilts/clang/host/linux-x86/+archive/refs/heads/main/clang-r547379.tar.gz
mkdir clang-r547379
tar -xzf clang-r547379.tar.gz -C clang-r547379/
```

### Clone and Build
```bash
git clone https://github.com/YOUR_USERNAME/kernel_xiaomi_sweet.git -b sixteen-ksu-next
cd kernel_xiaomi_sweet
git submodule update --init --recursive
./build.sh
```

When prompted, enter your device codename (e.g., `sweet`).

## Installation
1. Flash the generated ZIP file via TWRP/custom recovery
2. Install [KernelSU-Next Manager](https://github.com/KernelSU-Next/KernelSU-Next/releases)
3. Reboot and enjoy!

## Credits
- [TheHewra](https://github.com/TheHewra) - Original kernel source
- [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next) - Root solution
- Xiaomi - Device sources

## License
GPL-2.0
