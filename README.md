# Kernel for Xiaomi Redmi Note 10 Pro (sweet)

Custom kernel based on Linux 4.14.356 with KernelSU-Next integration.

## Features
- ✅ KernelSU-Next support
- ✅ Optimized for Xiaomi sweet (Redmi Note 10 Pro)
- ✅ Based on Android 4.14 kernel
- ✅ Easy build script included

## Supported Devices
- sweet (Redmi Note 10 Pro)
- sweetin (Redmi Note 10 Pro India)
- tucana
- toco
- phoenix
- davinci

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
# Clone the repository
git clone https://github.com/Mryassinov/kernel_xiaomi_sweet.git -b sixteen-ksu-next
cd kernel_xiaomi_sweet

# Initialize KernelSU-Next submodule
git submodule update --init --recursive

# Build the kernel
./build.sh
```

When prompted, enter your device codename (e.g., `sweet`).

The script will automatically:
- Configure the kernel
- Compile using all CPU cores
- Create a flashable ZIP file

### Clean Build
```bash
./build.sh --clean
```

## Installation
1. Copy the generated ZIP file to your device
2. Boot into TWRP/custom recovery
3. Flash the ZIP file
4. Install [KernelSU-Next Manager](https://github.com/KernelSU-Next/KernelSU-Next/releases)
5. Reboot and enjoy root access!

## Download
Check the [Releases](https://github.com/Mryassinov/kernel_xiaomi_sweet/releases) section for pre-built kernels.

## Credits
- [TheHewra](https://github.com/TheHewra) - Original kernel source
- [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next) - Kernel-based root solution
- Xiaomi - Device sources

## License
GPL-2.0
