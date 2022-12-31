# RV-MINI Programming Assignment
This project is the programming assignment of the class RV-MINI  

To install packages, run
```bash
sudo apt install openjdk-8-jdk build-essential git m4 scons zlib1g zlib1g-dev libprotobuf-dev protobuf-compiler libprotoc-dev libgoogle-perftools-dev python-dev python -y
sudo apt install git vim autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc python3 python3-pip -y
echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | sudo tee /etc/apt/sources.list.d/sbt.list
echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | sudo tee /etc/apt/sources.list.d/sbt_old.list
curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
sudo apt-get update
sudo apt-get install sbt -y
```


To initialize, run
```bash
git clone https://github.com/jingpoyan/rvmini-pa.git
git submodule update --init --recursive
```
To build riscv-tools-priv1.7, run
```bash
export RISCV=/path/to/install/dir
export PATH=$RISCV/bin:$PATH

cd riscv-mini
bash download-riscv-tools.sh

# build riscv-gnu-toolchain-priv1.7
cd riscv-tools-priv1.7/riscv-gnu-toolchain/
./configure --prefix=$RISCV --with-xlen=32
make -j8

# build riscv-fesvr
cd ../riscv-fesvr/
./configure --prefix=$RISCV
make -j8
make install

# build riscv-tests(ISA and benchmarks)
cd ../riscv-tests/isa/
make RISCV_PREFIX=riscv32-unknown-elf- XLEN=32
cd ../benchmarks/
make RISCV_PREFIX=riscv32-unknown-elf- XLEN=32
```
To build gem5, run
```
cd gem5
python3 `which scons` build/RISCV/gem5.opt -j8
```
The following subprojects/components are included.
* [riscv-mini](https://github.com/jingpoyan/riscv-mini.git)
* [rvmini_opcodes](https://github.com/jingpoyan/rvmini_opcodes.git)
* [gem5](https://gem5.googlesource.com/public/gem5)
