# DDK_build_the_kernel
Use the cross compiler to build the linux kernel. &nbsp;

uname -a <br/>
Linux ubuntu 5.13.0-28-generic #31~20.04.1-Ubuntu SMP Wed Jan 19 14:08:10 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux &nbsp;

cd /home/denny/Desktop/ <br/>
git clone git://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git linux <br/>
cd /home/denny/Desktop/linux &nbsp;

Unable to find the ncurses package. <br/>
Install ncurses (ncurses-devel or libncurses-dev depending on your distribution). <br/>
sudo apt-get install libncurses5-dev libncursesw5-dev  &nbsp;

Command 'gcc' not found, but can be installed with: <br/>
sudo apt gcc &nbsp;

/bin/sh: 1: flex: not found <br/>
sudo apt-get install flex -y &nbsp;

/bin/sh: 1: bison: not found <br/>
sudo apt-get install bison -y &nbsp;

cd /home/denny/Desktop/linux &nbsp;

# Method 1
make ARCH=arm menuconfig <br/>
save <br/>
exit &nbsp;

ls -al <br/>
You can see .config has been created. &nbsp;

# Method 2
make ARCH=arm multi_v7_defconfig &nbsp;

multi_v7_defconfig is from /home/denny/Desktop/linux/arch/arm/ &nbsp;

# Build the kernel
make -j 4 ARCH=arm CROSS_COMPILE=arm-cortex_a8-linux-gnueabihf- zImage &nbsp;

/home/denny/Desktop/linux/include/config/auto.conf <br/>
  SYNC    include/config/auto.conf.cmd <br/>
scripts/Kconfig.include:39: compiler 'arm-cortex_a8-linux-gnueabihf-gcc' not found <br/>
make[2]: *** [scripts/kconfig/Makefile:77: syncconfig] Error 1 <br/>
make[1]: *** [Makefile:619: syncconfig] Error 2 <br/>
make: *** [Makefile:721: include/config/auto.conf.cmd] Error 2 &nbsp;

It means you should build the arm-cortex_a8-linux-gnueabihf-gcc first. &nbsp;
