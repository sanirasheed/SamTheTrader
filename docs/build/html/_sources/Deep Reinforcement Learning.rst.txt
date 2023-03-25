.. _vcpkg: https://vcpkg.io/en/index.html

.. _CMake: https://cmake.org/

.. _ here: https://cmake.org/

.. _here: https://github.com/microsoft/vcpkg

.. _here.: https://pytorch.org/

.. _WSL (Version 2): https://docs.microsoft.com/en-us/windows/wsl/install

.. _LibTorch (PyTorch): https://pytorch.org/

.. _MobaXTerm: https://mobaxterm.mobatek.net/

.. role:: python(code)
  :language: python
  :class: highlight

Deep reinforcement learning
###########################

A deep reinforcement learning framework.

Prerequisites
-------------

`CMake`_
^^^^^^^^
    CMake is used to build the system. A comprehensive installation guide can be found` here`_. Alternatively, paste the
    lines below into your terminal::

        wget https://github.com/Kitware/CMake/releases/download/v3.23.0-rc2/cmake-3.23.0-rc2.tar.gz
        tar -xf cmake-3.23.0-rc2.tar.gz
        cd cmake-3.23.0-rc2
        ./bootstrap -- -DCMAKE_BUILD_TYPE:STRING=Release
        make
        make install

    If any permission errors are encountered, try appending :python:`sudo` in front of each command (e.g.
    :python:`sudo make` instead of :python:`make`).

`Vcpkg`_
^^^^^^^^
    vcpkg makes managing external libraries easy. A comprehensive installation guide can be found `here`_.
    Alternatively, paste the lines below into your terminal::

        cd ~
        git clone https://github.com/microsoft/vcpkg
        ./vcpkg/bootstrap-vcpkg.sh

    If any permission errors are encountered, try appending :python:`sudo` in front of each command (e.g.
    :python:`sudo make` instead of :python:`make`).

`LibTorch (PyTorch)`_
^^^^^^^^^^^^^^^^^^^^^^
    PyTorch provides deep learning functionality. A comprehensive installation guide can be found `here.`_ Alternatively,
    paste the lines below into your terminal::

        cd ~
        wget https://download.pytorch.org/libtorch/nightly/cpu/libtorch-shared-with-deps-latest.zip
        unzip libtorch-shared-with-deps-latest.zip

    If any permission errors are encountered, try appending :python:`sudo` in front of each command (e.g.
    :python:`sudo make` instead of :python:`make`).

Subrepositories
###############
    The :python:`gym`, :python:`deep_learning`, and :python:`tuner` repositories need to be cloned into the home directory,
    under a folder named :python:`sam`. This can be done with the instructions below::

        cd ~
        mkdir sam
        cd sam
        git clone https://github.com/ava6969/gym.git
        git clone https://github.com/ava6969/deep_learning.git
        git clone https://github.com/ava6969/tuner.git

Setting up Deep Reinforcement Learning
######################################
    Before getting started, it should be known that this library has been primarily tested and built in a Linux
    environment, so directly building on a Windows system is inadvisable. If you are using Windows, it's best to use
    `WSL (Version 2)`_, plus a XWindow package like `MobaXTerm`_.

    To begin, clone the repo and enter it::

        git clone https://github.com/ava6969/deep_rl.git
        cd deep_rl

    Install dependencies::

        ~/vcpkg/vcpkg install "@vcpkg_deps.txt"

    Build the library::

        mkdir cmake-build-debug
        cd cmake-build-debug
        cmake -DCMAKE_C_COMPILER=gcc -DCMAKE_CXX_COMPILER=g++ -DCMAKE_MAKE_PROGRAM=make ..
        cmake --build .

    And you're done!