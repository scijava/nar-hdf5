NAR-HDF5
========

This project is a [nar-maven-plugin](http://maven-nar.github.io/index.html) distribution of the [HDF5 native library](http://www.hdfgroup.org/HDF5/).

The goal of this project is to provide HDF5 native code across a variety of AOL (architecture-operating system-linker) configurations, using the SciJava [native-lib-loader](https://github.com/scijava/native-lib-loader) to automatically inject the wrapped native code onto the `java.library.path`.

This allows the SciJava framework to consume this HDF5 code automatically, without requiring prior knowledge of the HDF5 native library.

CURRENT VERSION
---------------

HDF5-1.8.14


Support AOLs
------------

* Windows amd64 link v12.00.31101.0 cl v18.00.31101 (MSVS 12.0)

Adding additional AOL support
-----------------------------

1. A libhdf5.settings file needs to be generated, e.g. by configuring with CMake on Windows.
2. The H5detect and H5make_libsettings programs need to be compiled.
3. Add the executables from 2 and settings file from 1 to `/bin`
4. Add configuration for `exec-maven-plugin` to the `pom.xml` to call the appropriate programs from 2 and store their output as `.c` files. (model after existing configuration)


BUGS
----

Please submit bugs as [GitHub issues](https://github.com/scijava/nar-hdf5/issues).
