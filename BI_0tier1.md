_**Note:**_ These instructions are no longer maintained. Please refer [here](https://www.ibm.com/community/z/open-source-software/) for latest information.

# Building ZeroTier

The instructions provided below specify the steps to build ZeroTier version 1.10.2 on Linux on IBM Z for following distributions:

* RHEL (7.8, 7.9, 8.4, 8.6, 8.7, 9.0, 9.1)
* SLES (12 SP5, 15 SP3,SP4)
* Ubuntu (18.04, 20.04, 22.04, 22.10)

_**General Notes:**_ 	 
* _When following the steps below please use a standard permission user unless otherwise specified._
* _A directory `/<source_root>/` will be referred to in these instructions, this is a temporary writeable directory anywhere you'd like to place it._
```
export SOURCE_ROOT=/<source_root>/
```
#### Step 1: Install the Dependencies 

* RHEL Distros
  ```bash
  sudo yum install -y gcc gcc-c++ make cmake wget tar bzip2 binutils-devel git patch iputils zlib-devel diffutils
  ```
* SLES Distros
  ```bash
  sudo zypper install -y wget git tar make cmake gcc gcc-c++ binutils-devel patch which bzip2 iputils
  sudo zypper in libz1 zlib-devel
  ```
* UBUNTU Distros
  ```bash
 sudo apt-get update  
sudo apt-get install -y gcc g++ make git tar cmake wget patch binutils bzip2 iputils-ping libz-dev diffutils
  ```
#### Step 2: Install GCC

* SLES 12
```
sudo zypper install -y gcc gcc5 gcc5-c++
sudo ln -sf /usr/bin/gcc-5 /usr/bin/gcc
sudo ln -sf /usr/bin/g++-5 /usr/bin/g++
sudo ln -sf /usr/bin/gcc /usr/bin/cc
```
* Install GCC-12.1.0
	```
	wget http://ftp.gnu.org/gnu/gcc/gcc-12.1.0/gcc-12.1.0.tar.gz
	tar -xzf gcc-12.1.0.tar.gz  
	cd gcc-12.1.0/  
	./contrib/download_prerequisites  
	cd $SOURCE_ROOT/  
	mkdir gcc_build  
	cd gcc_build/  
	../gcc-12.1.0/configure --prefix="/opt/gcc" --enable-shared --with-system-zlib --enable-threads=posix --enable-__cxa_atexit --enable-checking --enable-gnu-indirect-function --enable-languages="c,c++" --disable-bootstrap --disable-multilib  
	make -j 6 
	sudo make install  
	export PATH=/opt/gcc/bin:$PATH  
	sudo ln -sf /opt/gcc/bin/gcc /usr/bin/gcc
	export C_INCLUDE_PATH=/opt/gcc/lib/gcc/s390x-ibm-linux-gnu/12.1.0/include  
	export CPLUS_INCLUDE_PATH=/opt/gcc/lib/gcc/s390x-ibm-linux-gnu/12.1.0/include
	sudo ln -sf /opt/gcc/lib64/libstdc++.so.6.0.24 /lib64/libstdc++.so.6
	export LD_LIBRARY_PATH='/opt/gcc/$LIB'
	```

#### Step 3: Download and Install ZeroTier
* Download ZeroTier source code
  ```bash
  cd $SOURCE_ROOT/
  git clone https://github.com/zerotier/ZeroTierOne.git
  cd ZeroTierOne
  git checkout 1.10.2
  ```
* Build and Test ZeroTier  
  ```bash  
  cd $SOURCE_ROOT/ZeroTierOne
  make
  make selftest
  ./zerotier-selftest
  sudo make install
  export PATH=/usr/sbin:$PATH
  ```
* Show Zerotier version
  ```bash
  zerotier-one -v
  ```

#### Step 3:  Verify ZeroTier(Optional)  
* Start Zerotier-one Service
  ```bash
  sudo zerotier-one -d
  ```  
_**Note:** A home folder for your system will automatically be created at `/var/lib/zerotier-one`._

* Use below command to authorize a non-privileged user on Linux
  ```bash
  sudo cat /var/lib/zerotier-one/authtoken.secret >>.zeroTierOneAuthToken
  chmod 0600 .zeroTierOneAuthToken
  ```
_**Note:** Run above commands from the home directory of the user to authorize._

* Use command line interface (zerotier-cli) to make API calls for standard things like joining and leaving networks
  ```bash
  zerotier-cli -h
  ```

  * Display status info
  ```bash
  sudo zerotier-cli info
  ```
	
  * Join a Network
  ```bash
  sudo zerotier-cli join <Network-ID>
  ```
  To join `Earth` public Network run command: `sudo zerotier-cli join 8056c2e21c000001`. User will receive a `200 join OK` message after successful join.

  * List all networks
  ```bash
  sudo zerotier-cli listnetworks
  ```

  * Verify Connectivity
  ```bash
  ping <network-name>
  ```
  To verify connection with `Earth` public Network run command: `ping earth.zerotier.net`, If replies are being returned from `Earth` Network (as shown in the output shown below), then your host is now connected.  
  ```bash
  Output:
	PING earth.zerotier.net (28.234.20.174) 56(84) bytes of data.
	64 bytes from 28.234.20.174: icmp_seq=1 ttl=64 time=521 ms
	64 bytes from 28.234.20.174: icmp_seq=2 ttl=64 time=140 ms
	64 bytes from 28.234.20.174: icmp_seq=3 ttl=64 time=120 ms
	64 bytes from 28.234.20.174: icmp_seq=4 ttl=64 time=121 ms
	64 bytes from 28.234.20.174: icmp_seq=5 ttl=64 time=192 ms
  ```
  
  * Leave a Network
  ```bash
  sudo zerotier-cli leave <Network-ID>
  ```
  To Leave `Earth` public Network run command: `sudo zerotier-cli leave 8056c2e21c000001`. User will receive a `200 leave OK` message after successful run.   
  
## References
https://github.com/zerotier/ZeroTierOne

https://www.zerotier.com/

https://zerotier.atlassian.net/wiki/spaces/SD/pages/7110657/General+Help

https://zerotier.atlassian.net/wiki/spaces/SD/pages/7536656/Running+ZeroTier+in+a+Docker+Container
