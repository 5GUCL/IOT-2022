## Deploy the GUI IoT Application 
# IOT Setup

    For Deploying the IOT use case we need to have the following pre-requirements 

## Install the Ubuntu 18.04 and above

    lsb_release -a # To check the ubuntu version
    sudo apt-get update
    sudo apt-get upgrade

    Follow the Document 5GIOTENV001.pdf available in Gitlab and install all the packages and dependencies provided

## Make sure we use the latest versions of Python3 and PIP3. 

    sudo apt install -y python3
    sudo apt install -y python3-pip

## Install all pip packages using

    pip3 install <package name>
    sudo apt install -y build-essential libssl-dev libffi-dev python3-dev

## Install and setup the Python virtual environment

    sudo apt install -y python3-venv
    mkdir environment
    cd environment
    python3 -m venv my_env   !!! If you got a error here it means your environemnt is not installed and set up
    ls my_env

## Install and upgrade all the packages
    sudo apt-get install python<version>

## Install Poetry using

    pip3 install poetry 
     (OR)
    sudo apt install curl
    curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py| python3 !!! If any issue arises go to the debug section at eop
    source $HOME/.poetry/env
    poetry --verison 

## Follow Document v2.0.0_21_10_21/sdl-modbus/docs/README.md file

## Install Redis
    sudo apt-get update
    sudo apt-get install redis-server

## Install HDF5:
        sudo apt-get update -y
        sudo apt-get install -y hdf5-tools

## Install ZeroMQ:
    sudo apt-get update
    sudo apt-get install libzmq3-dev

## Install Libsodium:
    sudo apt-get update -y
    sudo apt-get install -y libsodium-dev

## Install Nettle Crypto Library:
    sudo apt-get update -y
    sudo apt-get install -y nettle-dev

## Install C/C++ cross compilers:
    sudo apt update
    sudo apt install build-essential
    sudo apt-get install manpages-dev

## Install Clang compiler:

    wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key | sudo apt-key add -
    sudo apt-add-repository "deb http://apt.llvm.org/xenial/ llvm-toolchain-xenial-6.0 main"
    sudo apt-get update
    sudo apt-get install -y clang-6.0

## Install Codelite IDE:
    sudo apt-get purge codelite codelite-plugins
    sudo sh -c 'echo "deb http://repos.codelite.org/ubuntu/ xenial universe" >> /etc/apt/sources.list.d/codelite.list'
    sudo apt-key adv –fetch-keys http://repos.codelite.org/CodeLite.asc
    sudo apt-get update
    sudo apt-get install codelite wxcrafter
    sudo apt-get install codelite (!!! If bug arises go to debug section)
    (or)
    sudo apt-get install codelite
## Install Important packages for deployement before you start

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get dist-upgrade
    sudo reboot
    sudo apt-get install binutils
    sudo apt-get install apt-transport-https ca-certificates
    sudo apt-get install build-essential software-properties-common -y
    sudo apt-get update
    sudo apt-get install gcc
    gcc --version
    g++ --version
    sudo apt-get install libssl-dev
    sudo apt-get install build-essential binutils-doc autoconf flex bison libjpeg-dev libfreetype6-dev zlib1g-dev libgdbm-dev libncurses5-dev automake libtool libffi-dev curl git tmux gettext cmake
    sudo apt-get install libxml2-dev libxslt-dev xutils-dev
    sudo apt-get install libboost-all-dev
    sudo apt-get install python-dev
    sudo apt-get install python3-dev
    sudo apt-get install cython
    sudo apt-get install cython3
    sudo apt-get install libdbus-1-dev libdbus-glib-1-dev
    sudo apt-get install clang
    sudo apt-get install python-pip
    sudo apt-get install python3-pip
    sudo apt-get install libblas-dev liblapack-dev libatlas-base-dev
    sudo apt-get install vim
    sudo apt-get install tree
    sudo apt-get install libreadline-dev
    sudo apt-get install libgc-dev
    sudo apt-get install liburcu-dev
    sudo apt-get install check
    sudo apt-get install libcurl4-openssl-dev 
    sudo apt-get install libcurl4-gnutls-dev
    sudo apt-get install software-properties-common
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get dist-upgrade
    
!!! If any error occurs check your internet connection and remove proxy OR remove proxy for particular package

## Build Set-up (IMPO)
    First Download v2.0.0_21_10_21 from google drive link
    Go to v2.0.0_21_10_21/sdl-modbus/docs/README.md

## InstaLl ```OpenGL development libraries``` [start from line number 254]

    sudo apt-get install build-essential libgl1-mesa-dev  # Debian, Ubuntu
    sudo apt-get install libglew-dev libsdl2-dev libsdl2-image-dev libglm-dev libfreetype6-dev  # Debian, Ubuntu
    sudo apt-get install libglfw3-dev
    sudo apt-get install libfreetype6 libfreetype6-dev

### Create a directory[REPO] in folder[IOT]
    mkdir REPO
    cd REPO
    
## Install ```libmodbus```
    Source: https://github.com/stephane/libmodbus/ 
    git clone --recursive --recurse-submodules https://github.com/stephane/libmodbus.git
    cd libmodbus
    export CFLAGS+=" -Os "
    export CPPFLAGS+=" -g -Wall -fPIC "
    export CXXFLAGS+=" -g -Wall -fPIC "
    ./autogen.sh
    ./configure  --enable-static
    make
    make check
    sudo make install
    sudo ldconfig


## Install ```GLFW```
    wget https://github.com/glfw/glfw/archive/refs/tags/3.3.4.zip
    unzip 3.3.4.zip
    cd glfw-3.3.4/
    mkdir build && cd build && cmake .. && make -j4
    sudo make install
    sudo apt install cmake-curses-gui
    ccmake ..[press enter and change it into ON press g to configure and save and exit]
    
## Install ```GL3W```
    git clone https://github.com/skaslev/gl3w.git
    cd gl3w
    python3 gl3w_gen.py
    mkdir build && cd build && cmake .. && make -j4
    sudo make install

### Install ```JAVA```  and set path
    sudo apt update
    java -version
    sudo apt install default-jre
    sudo apt install openjdk-11-jre-headless
    sudo apt install openjdk-8-jre-headless
    sudo apt install default-jdk
    javac -version


### Install ```HDF5```
    wget https://www.hdfgroup.org/downloads/hdf5/source-code/
    Download the file and save it into REPO and Unzip the file
    unzip or untar  hdf5-1.12.1/ and save it into REPO directory
    cd  hdf5-1.12.1/
    export CFLAGS+=" -Os "
    export CPPFLAGS+=" -g -Wall -fPIC "
    export CXXFLAGS+=" -g -Wall -fPIC "
    ./configure --prefix=/usr/local \
            --with-zlib \
            --enable-build-mode=production \
            --with-pic\
            --enable-hl \
            --enable-cxx \
            --enable-build-all \
            --enable-java
    ./configure  --enable-static
    make
    make check
    sudo make install
    sudo ldconfig

### Install ```libuv``` in REPO
    git clone https://github.com/libuv/libuv.git
    cd libuv
    export CFLAGS+=" -Os "
    export CPPFLAGS+=" -g -Wall -fPIC "
    export CXXFLAGS+=" -g -Wall -fPIC "
    ./autogen.sh 
    ./configure 
    make -j4
    sudo make install
    sudo ldconfig

### Change necessary changes for ```CLANG Compiler```
    Go to vi .bashrc
    Add 
    export CC=/usr/bin/clang
    export CXX=/usr/bin/clang++

### Install Hiredis must needed package SDL-Modbus in REPO
    git clone https://github.com/redis/hiredis
(or)sudo apt-get install redis-server
    cd hiredis
    mkdir build
    cd build
    cmake ..
    make -j4
    make test
    sudo make install
    sudo ldconfig


### IMPORTANT : 
    export CFLAGS+=" -Os "
    export CPPFLAGS+=" -g -Wall -fPIC "
    export CXXFLAGS+=" -g -Wall -fPIC "Build SDL-Modbus 
    Go to v2.0.0_21_10_21/sdl-modbus
    remove the build
    rm -rf build
    Then make a directory and again build the process
    mkdir build
    cd build
    cmake ..
    make -j4  #error







### Debugs

    To debug Poetry related issue run following command

    source $HOME/.poetry/env

![parameter](screenshots/pip3poetryerror.png)
![parameter](screenshots/poetrydebug2.png)
![parameter](screenshots/poetrysouce.png)
![parameter](screenshots/codelitebug.png)
![parameter](screenshots/sdlerror.png)
![parameter](screenshots/sdlerror2.png)
![parameter](screenshots/sdlerror3.png)
