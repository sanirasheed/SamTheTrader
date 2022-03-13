.. _vcpkg: https://vcpkg.io/en/index.html

.. _CMake: https://cmake.org/

.. _LibTorch (PyTorch): https://pytorch.org/

.. role:: python(code)
  :language: python
  :class: highlight

Deep Learning
#############

    This library provides C++-based deep learning modules for reinforcement learning,
    such as ResNet blocks, self attention layers, and variational autoencoders.

Prerequisites
-------------

`CMake`_
^^^^^^^^
    CMake is used to build the system. A comprehensive installation guide can be found here. Alternatively,
    paste the lines below into your terminal::

        wget https://github.com/Kitware/CMake/releases/download/v3.23.0-rc2/cmake-3.23.0-rc2.tar.gz
        tar -xf cmake-3.23.0-rc2.tar.gz
        cd cmake-3.23.0-rc2
        ./bootstrap -- -DCMAKE_BUILD_TYPE:STRING=Release
        make
        make install

    If any permission errors are encountered, try appending sudo in front of each command (e.g. sudo make instead of make).

`Vcpkg`_
^^^^^^^^
    vcpkg makes managing external libraries easy. A comprehensive installation guide can be found here. Alternatively,
    paste the lines below into your terminal::

        cd ~
        git clone https://github.com/microsoft/vcpkg
        ./vcpkg/bootstrap-vcpkg.sh

    If any permission errors are encountered, try appending sudo in front of each command (e.g. sudo make instead of
    make)

`LibTorch (PyTorch)`_
^^^^^^^^^^^^^^^^^^^^^^
    PyTorch provides deep learning functionality. A comprehensive installation guide can be found here. Alternatively,
    paste the lines below into your terminal::

        cd ~
        wget https://download.pytorch.org/libtorch/nightly/cpu/libtorch-shared-with-deps-latest.zip
        unzip libtorch-shared-with-deps-latest.zip

    If any permission errors are encountered, try appending :python:`sudo` in front of each command (e.g. sudo make
    instead of make).

Setting up Deep Learning
########################
    Before getting started, it should be known that this library has been primarily tested and built in a Linux
    environment, so directly building on a Windows system is inadvisable. If you are using Windows, it's best to use WSL
    (Version 2).
    To begin, clone the repo and enter it::

        git clone https://github.com/ava6969/deep_learning.git
        cd deep_learning

    Install dependencies::

        ~/vcpkg/vcpkg install "@vcpkg_deps.txt"

    Build the library::

        export Torch_DIR=~/
        mkdir cmake-build-debug
        cd cmake-build-debug
        cmake -DCMAKE_C_COMPILER=gcc -DCMAKE_CXX_COMPILER=g++ -DCMAKE_MAKE_PROGRAM=make ..
        cmake --build .

    And you're done!