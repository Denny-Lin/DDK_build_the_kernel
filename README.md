# DDK_build_the_kernel
* Use the cross compiler to build the linux kernel.

uname -a <br/>
Linux ubuntu 5.13.0-28-generic #31~20.04.1-Ubuntu SMP Wed Jan 19 14:08:10 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux <br/>
&nbsp;

Unable to find the ncurses package. <br/>
Install ncurses (ncurses-devel or libncurses-dev depending on your distribution). <br/>
sudo apt-get install libncurses5-dev libncursesw5-dev  <br/>
&nbsp;

Command 'gcc' not found, but can be installed with: <br/>
sudo apt gcc <br/>
&nbsp;

/bin/sh: 1: flex: not found <br/>
sudo apt-get install flex -y <br/>
&nbsp;

/bin/sh: 1: bison: not found <br/>
sudo apt-get install bison -y <br/>
&nbsp;

# Method 1
