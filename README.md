# msvsdwc


Magic
Magic is an open-source VLSI layout tool.

Install steps:
```verilog

M4 preprocessor
$ sudo apt-get install m4
tcsh shell
$ sudo apt-get install tcsh
csh shell (note that Ubuntu has different csh and tcsh)
$ sudo apt-get install csh
Xlib.h
$ sudo apt-get install libx11-dev
If you wish to have the Tcl/Tk wrapper around magic (recommended) you will need to install the Tcl/Tk libraries. Version 8.5 or higher is highly recommended.
Tcl/Tk
$ sudo apt-get install tcl-dev tk-dev
The best graphics for Magic is the OpenGL interface ("magic -d OGL"), but since that is problematic for off-screen rendering on many systems, a good alternative is the Cairo graphics interface ("magic -d XR"). This is optional, but if you want to use it, you need the Cairo library development package:
Cairo
$ sudo apt-get install libcairo2-dev
The OpenGL interface itself may need these dependencies:
OpenGL
$ sudo apt-get install mesa-common-dev libglu1-mesa-dev
For the non-Tcl/Tk version only: The readline source makes reference to the `tputs` function which is provided by the ncurses library. Although the ncurses library is installed in Ubuntu, the include files to build against it are not, so the development version is required.
ncurses
$ sudo apt-get install libncurses-dev




$  git clone git://opencircuitdesign.com/magic
$  cd magic
$	 ./configure
$  make
$  sudo make install
```
More info can be found at http://opencircuitdesign.com/magic/index.html

Netgen
Netgen is a tool for comparing netlists, a process known as LVS, which stands for "Layout vs. Schematic"

Install steps:

$  git clone git://opencircuitdesign.com/netgen
$  cd netgen
$	./configure
$  make
$  sudo make install
More info can be found at http://opencircuitdesign.com/netgen/index.html

Xschem
Xschem is a schematic capture program

Install steps:
```verilog
$ sudo apt-get install flex
$ sudo apt-get install bison
$ sudo apt-get install libxpm-dev

$  git clone https://github.com/StefanSchippers/xschem.git xschem_git
$ cd xschem_git
$	./configure
$  make
$  sudo make install
```
More info can be found at http://repo.hu/projects/xschem/index.html




Ngspice
ngspice is the open-source spice simulator for electric and electronic circuits.

Install steps:

After downloading the tarball from https://sourceforge.net/projects/ngspice/files/ to a local directory, unpack it using:
```verilog

 $ sudo apt-get install libxaw7-dev
 
 
 
 $ tar -zxvf ngspice-37.tar.gz
 $ cd ngspice-37
 
 $ ../configure  --with-x --with-readline=yes --disable-debug
 $ make
 $ sudo make install
```
sudo apt-get install libxaw7-dev








open_pdk
Open_PDKs is distributed with files that support the Google/SkyWater sky130 open process description https://github.com/google/skywater-pdk. Open_PDKs will set up an environment for using the SkyWater sky130 process with open-source EDA tools and tool flows such as magic, qflow, openlane, netgen, klayout, etc.

Install steps:
```verilog
$  git clone git://opencircuitdesign.com/open_pdks
$  cd open_pdks
$	./configure --enable-sky130-pdk
$  make
$  sudo make install
```
