Fluid
=====

[![License](https://img.shields.io/badge/license-MPL2-blue.svg)](https://www.mozilla.org/en-US/MPL/2.0/)
[![GitHub release](https://img.shields.io/github/release/lirios/fluid.svg)](https://github.com/lirios/fluid)
[![Build Status](https://travis-ci.org/lirios/fluid.svg?branch=develop)](https://travis-ci.org/lirios/fluid)
[![GitHub issues](https://img.shields.io/github/issues/lirios/fluid.svg)](https://github.com/lirios/fluid/issues)
[![Maintained](https://img.shields.io/maintenance/yes/2018.svg)](https://github.com/lirios/fluid/commits/develop)

Fluid is a collection of cross-platform QtQuick components for building fluid and dynamic applications,
using the [Material Design](https://material.io/guidelines/) guidelines.

Online documentation is available at [liri.io](https://liri.io/docs/sdk/fluid/develop/).

We develop using the [git flow](https://danielkummer.github.io/git-flow-cheatsheet/) method
this means that the `develop` branch contains code that is being developed and might break
from time to time. If you want to check out a stable version just install one of the
releases or clone the `master` branch that has the latest released version.

![Desktop](.github/demo.png)

## Dependencies

Qt >= 5.10.0 with at least the following modules is required:

 * [qtbase](http://code.qt.io/cgit/qt/qtbase.git)
 * [qtdeclarative](http://code.qt.io/cgit/qt/qtdeclarative.git)
 * [qtquickcontrols2](http://code.qt.io/cgit/qt/qtquickcontrols2.git)
 * [qtgraphicaleffects](http://code.qt.io/cgit/qt/qtgraphicaleffects.git)
 * [qtsvg](http://code.qt.io/cgit/qt/qtsvg.git)
 * [qtdoc](http://code.qt.io/cgit/qt/qtdoc.git)

The following modules and their dependencies are required:

 * [cmake](https://gitlab.kitware.com/cmake/cmake) >= 3.10.0
 * [cmake-shared](https://github.com/lirios/cmake-shared.git) >= 1.0.0

## Build

```sh
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/path/to/prefix ..
make
make install # use sudo if necessary
```

Replace `/path/to/prefix` to your installation prefix.
Default is `/usr/local`.

You can also append the following options to the `cmake` command:

 * `-DFLUID_USE_SYSTEM_LCS:BOOL=ON`: Use a system-wide copy of LiriCMakeShared.
 * `-DFLUID_WITH_DOCUMENTATION:BOOL=OFF`: Do not build the documentation.
 * `-DFLUID_WITH_DEMO:BOOL=OFF`: Do not build the demo application.
 * `-DFLUID_WITH_QML_MODULES:BOOL=OFF`: Do not build QML modules.
 * `-DFLUID_INSTALL_ICONS:BOOL=OFF`: Embed icons into resources.

### Documentation

The HTML documentation is built unless `-DFLUID_WITH_DOCUMENTATION:BOOL=OFF` is
passed to cmake and it's installed into `<prefix>/share/doc/fluid/html`.

Open `<prefix>/share/doc/fluid/html/index.html` with a browser to read it.

## Installation

You can either install system-wide or per-project installation which
is essentially embedding Fluid in your project.

System-wide installations are usually performed by packagers who want
to redistribute Fluid in their Linux distro.

Per-project installation is most useful for mobile developers that
want to build Fluid alongside their project.

## System-wide installation

We assume that your distro installs QtQuick modules in `/usr/lib/qt/qml`
like `Arch Linux` does, please change the paths for your Linux distro.

The same goes for other operating systems.

From the root of the repository, run:

```sh
git submodule update --init --recursive
mkdir build
cmake -DCMAKE_INSTALL_PREFIX=/usr -DINSTALL_QMLDIR=lib/qt/qml ..
make
sudo make install
```

Please note that a system-wide installation is discouraged in most cases
because there's a risk to "pollute" your system with libraries not
managed by a package manager.

## Per-project installation

You can embed Fluid in your project and build it along your app.

We have an example with qmake in `examples/perproject/minimalqmake`
and another one for qbs in `examples/perproject/minimalqbs`.

## Licensing

Licensed under the terms of the Mozilla Public License version 2.0.
