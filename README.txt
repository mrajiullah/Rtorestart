*Download the 3.7 kernel from kernel.org and extract it in a working folder

* Copy the patch "rto_restart.patch" to the folder where you unpacked the kernel.
  Enter the folder where you unpacked the kernel and patch the kernel.
	# patch -p1 < rto_restart.patch

* Install required packages to build the kernel (assumes Debian-based Linux)
	# apt-get install build-essential

* Copy old kernel config to the folder containing the new (patched) kernel source
        # cp /boot/config-`uname -r` .config 

* Configure the new kernel
  	# make oldconfig

* Compile the kernel (n should be one more than your number of cores)
	# make -jn

* Have coffee

* Install compiled kernel
	# sudo make modules_install
	# sudo make install
	# sudo make headers_install

* Reboot the kernel you just built/installed

