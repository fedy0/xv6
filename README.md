# xv6
Build xv6 Kernel for RISCV & x86; then run on QEMU
<br><br>

## Prerequisites
```bash
sudo apt install git-all
sudo apt-get install autoconf automake autotools-dev curl python3 libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc zlib1g-dev libexpat-dev
```

## For RISC-V
```bash
mkdir risc-v
cd risc-v
git clone https://github.com/riscv/riscv-gnu-toolchain

mkdir /opt/riscv

./configure --prefix=/opt/riscv
make linux

export PATH="$PATH:/opt/riscv/bin" >> ~/.bashrc
source ~/.bashrc

sudo apt-get install qemu qemu-system-riscv64
sudo apt-get install libc6-dev-riscv64-cross
git clone https://github.com/mit-pdos/xv6-riscv.git
chmod 700 -R xv6-riscv
cd xv6-riscv
make
make qemu
```

## For x86
```bash
sudo apt-get install qemu qemu-system-x86
sudo apt-get install libc6-dev:i386
git clone https://github.com/mit-pdos/xv6-public.git
chmod 700 -R xv6-public
cd xv6-public
make
make qemu
```
