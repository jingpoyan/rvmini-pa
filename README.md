# RV-MINI Programming Assignment
This project is the programming assignment of the class RV-MINI  

To install packages, run
```bash
sudo apt install openjdk-8-jdk build-essential git m4 scons zlib1g zlib1g-dev libprotobuf-dev protobuf-compiler libprotoc-dev libgoogle-perftools-dev python-dev python -y
sudo apt-get install git vim autoconf automake autotools-dev curl libmpc-dev libmpfr-dev libgmp-dev gawk build-essential bison flex texinfo gperf libtool patchutils bc python3 python3-pip -y
echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | sudo tee /etc/apt/sources.list.d/sbt.list
echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | sudo tee /etc/apt/sources.list.d/sbt_old.list
curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
sudo apt-get update
sudo apt-get install sbt -y
```


To initialize, run
```bash
git submodule update --init --recursive
```


The following subprojects/components are included.
* [riscv-mini](https://github.com/jingpoyan/riscv-mini.git)
* [rvmini_opcodes](https://github.com/jingpoyan/rvmini_opcodes.git)
* [gem5](https://gem5.googlesource.com/public/gem5)

