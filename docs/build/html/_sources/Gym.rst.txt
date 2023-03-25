.. _gym: https://github.com/ava6969/gym

.. _CMake: https://cmake.org/

.. _Vcpkg: https://vcpkg.io/en/index.html

.. _here: https://github.com/microsoft/vcpkg

.. _PyTorch: https://pytorch.org/

.. _here.: https://github.com/microsoft/vcpkg

.. _WSL (Version 2): https://docs.microsoft.com/en-us/windows/wsl/install

.. _MobaXTerm: https://mobaxterm.mobatek.net/

.. _Arcade Learning Environment: https://github.com/mgbellemare/Arcade-Learning-Environment

.. role:: python(code)
  :language: python
  :class: highlight


Getting Started with Gym
=============================
**The Gym is a toolkit where the reinforcement learning algorithms are developed and compared**.
The `gym`_ library is a collection of test problems -environments- that you can use to work out your reinforcement learning algorithms.
These environments have a shared interface, allowing you to write general algorithms.







Prerequisites:
--------------

`CMake`_
+++++++++
CMake is used to build the system. A comprehensive installation guide can be found here. Alternatively, paste the lines below into your terminal::

    wget https://github.com/Kitware/CMake/releases/download/v3.23.0-rc2/cmake-3.23.0-rc2.tar.gz
    tar -xf cmake-3.23.0-rc2.tar.gz
    cd cmake-3.23.0-rc2
    ./bootstrap -- -DCMAKE_BUILD_TYPE:STRING=Release
    make
    make install

If any permission errors are encountered, try appending *sudo* in front of each command (e.g. :python:`sudo make` instead of :python:`make`).

`Vcpkg`_
+++++++++

Vcpkg makes managing external libraries easy. A comprehensive installation guide can be found `here`_. Alternatively, paste the lines below into your terminal::

    cd ~
    git clone https://github.com/microsoft/vcpkg
    ./vcpkg/bootstrap-vcpkg.sh


`PyTorch`_
+++++++++++

PyTorch provides deep learning functionality. A comprehensive installation guide can be found `here.`_ Alternatively, paste the lines below into your terminal::

    cd ~
    wget https://download.pytorch.org/libtorch/nightly/cpu/libtorch-shared-with-deps-latest.zip
    unzip libtorch-shared-with-deps-latest.zip

`Arcade Learning Environment`_
++++++++++++++++++++++++++++++

ALE provides Atari emulation. A comprehensive installation guide can be found clicking on the link above. Alternatively, paste the lines below into your terminal::

    cd ~
    git clone https://github.com/mgbellemare/Arcade-Learning-Environment.git
    cd Arcade-Learning-Environment
    mkdir build && cd build
    cmake ../ -DCMAKE_BUILD_TYPE=Release
    cmake --build . --target install

If any permission errors are encountered, try appending sudo in front of each command (e.g. sudo make instead of make).


Setting up Gym
==============
Before getting started, it should be known that this library has been primarily tested and built in a Linux environment, so directly building on a Windows system is inadvisable. If you are using Windows, it's best to use `WSL (Version 2)`_, plus a XWindow package like `MobaXTerm`_.
To begin, clone the repo and enter it::

    git clone https://github.com/ava6969/gym.git
    cd gym

Install dependencies:
----------------------
Use the code below to install the necessary dependencies::

    sudo apt-get install bison
    ~/vcpkg/vcpkg install "@vcpkg_deps.txt"

Build the library:
-------------------
Now use this code to build the library::

    mkdir /cmake-build-debug/
    cd cmake-build-debug
    cmake -DCMAKE_C_COMPILER=gcc -DCMAKE_CXX_COMPILER=g++ -DCMAKE_MAKE_PROGRAM=make ..
    cmake --build ..


**And you're done!**




