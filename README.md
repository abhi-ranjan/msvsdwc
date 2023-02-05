# msvsdwc

## *Table of Contents*

* [Week 0](#week-0)
     + [Software Installation](#Software-Installation)
     + [Create inverter and perform pre-layout using xschem or ngspice](#Create-inverter-and-perform-pre-layout-using-xschem-or-ngspice)




# Week 0
---
## Software Installation
---
If we have a windows machine, install Oracle virtual box with Ubuntu 20.04 - RAM at least 4GB, hard-disk atleast 120GB.

- First update ubuntu with command 
```verilog
$ sudo apt-get update
$ sudo apt-get upgrade
```
- Then install the fillowing required file.

```verilog
$ sudo apt-get install m4
$ sudo apt-get install tcsh
$ sudo apt-get install csh
$ sudo apt-get install libx11-dev
$ sudo apt-get install tcl-dev tk-dev
$ sudo apt-get install libcairo2-dev
$ sudo apt-get install mesa-common-dev libglu1-mesa-dev
$ sudo apt-get install libncurses-dev
$ sudo apt-get install flex
$ sudo apt-get install bison
$ sudo apt-get install libxpm-dev
$ sudo apt-get install libxaw7-dev
$ sudo apt-get install lib32readline8 lib32readline-dev
$ sudo apt-get install libreadline-dev 
```
### Magic
Magic is an open-source VLSI layout tool.

Install steps:
```verilog
$  git clone git://opencircuitdesign.com/magic
$  cd magic
$	 ./configure
$  make
$  sudo make install
```
- [More Info](http://opencircuitdesign.com/magic/index.html)

### Netgen
Netgen is a tool for comparing netlists, a process known as LVS, which stands for "Layout vs. Schematic"

Install steps:
```verilog
$  git clone git://opencircuitdesign.com/netgen
$  cd netgen
$	./configure
$  make
$  sudo make install
```
- [More Info](http://opencircuitdesign.com/netgen/index.html)

### Xschem
Xschem is a schematic capture program

Install steps:
```verilog
$  git clone https://github.com/StefanSchippers/xschem.git xschem_git
$  cd xschem_git
$	./configure
$  make
$  sudo make install
```
- [More Info](http://repo.hu/projects/xschem/index.html)


### Ngspice
ngspice is the open-source spice simulator for electric and electronic circuits.

Install steps:

After downloading the tarball [from](https://sourceforge.net/projects/ngspice/files/) to a local directory, unpack it using(install 37 version):
```verilog

 $ tar -zxvf ngspice-37.tar.gz
 $ cd ngspice-37
 $ mkdir release
 $ cd release
 $ ./configure  --with-x --with-readline=yes --disable-debug
 $ make
 $ sudo make install
```

### open_pdk
Open_PDKs is distributed with files that support the Google/SkyWater sky130 open process description https://github.com/google/skywater-pdk. Open_PDKs will set up an environment for using the SkyWater sky130 process with open-source EDA tools and tool flows such as magic, qflow, openlane, netgen, klayout, etc.

Install steps:
```verilog
$  git clone git://opencircuitdesign.com/open_pdks
$  cd open_pdks
$	./configure --enable-sky130-pdk
$  make
$  sudo make install
```


### ALIGN

- First Install Python 3.7
```verilog
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.7
sudo apt install python3.10-venv
```

- Install gcc
```verilog
sudo apt install build-essential
```
## Create inverter and perform pre-layout using xschem or ngspice
---
### Verifiying the open_pdk installation
An initial working directory can be made by copying the required files as follows:
```verilog
$ mkdir week0
$ cd week0
$ mkdir inverter
$ cd inverter
$ mkdir mag
$ mkdir netgen
$ mkdir xschem
$ cd xschem
$ cp /usr/local/share/pdk/sky130A/libs.tech/xschem/xschemrc .
$ cp /usr/local/share/pdk/sky130A/libs.tech/ngspice/spinit .spiceinit
$ cd ../mag
$ cp /usr/local/share/pdk/sky130A/libs.tech/magic/sky130A.magicrc .magicrc
$ cd ../netgen
$ cp /usr/local/share/pdk/sky130A/libs.tech/netgen//sky130A_setup.tcl .
```

#### Checking if magic works
![Screenshot (2349)](https://user-images.githubusercontent.com/120498080/216841828-3dfd5129-c4ad-4af6-997d-8c8634d1e13d.png)

#### Checking if xschem works
![Screenshot (2346)](https://user-images.githubusercontent.com/120498080/216841917-17b9de64-f540-4e59-ba36-c280df58d01f.png)

#### Checking if netgen works
![Screenshot (2347)](https://user-images.githubusercontent.com/120498080/216841939-96bf7b43-b927-4fce-93b9-8e35eb73e2cb.png)

#### Checking if ngspice works
![Screenshot (2348)](https://user-images.githubusercontent.com/120498080/216841960-9d9aa965-ac18-459c-9c5c-ed28e1804fde.png)

### Creating inverter schematic using xschem
# Reference
- [Installing Tools](https://github.com/yathAg/Physical_Verification_SKY130A#Chapter-0---Getting-the-tools)
- [Installing ALIGN](https://github.com/sanampudig/OpenFASoC/tree/main/AUXCELL)
- [Creating Inverter](https://github.com/yathAg/Physical_Verification_SKY130A#Chapter-1---Understanding-the-design-flow)
