A set of C++ classes to easily handle serial ports across different platforms, built on top of boost.asio, created by Terraneo Federico in September 2009, distributed under Boost Software License, Version 1.0.

This is a fork by ericfont from upstream (https://github.com/fedetft/serial-port) with modified directory structure and CMakeLists.txt to build as a library so it can be included in other projects (such as a submodule). Note the Qt example 5 was removed because Qt library is too big of a dependency for a simple library. (Ideally this could be turned into a vcpkg library.)
