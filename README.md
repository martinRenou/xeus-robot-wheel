# Xeus-robot-wheel

This project holds the recipe for building PyPI wheels for the [xeus-robot](https://github.com/jupyter-xeus/xeus-robot) project.

The continuous integration builds and tests wheels for

 - Linux (`manylinux2010_x86_64`),
 - OS X (`Xcode 9.4.1`),
 - and Windows (x64).

## Building the manylinux wheels

Building the manylinux wheels requires `docker`. To build manylinux2010 wheels, clone the repository, and run:

```bash
docker run --rm -e PLAT=manylinux2010_x86_64 -v `pwd`:/io quay.io/pypa/manylinux2010_x86_64 /io/scripts/build-wheels.sh
```

from the root of the source directory.

Built manylinux wheels for Python 3.7, 3.8, and 3.9 are placed into the `wheelhouse` directory.

## Building the Windows wheels

The following packages must be installed in the environment to build the xeus-robot wheel on windows:

- `perl` (required to build `OpenSSL` on Windows)
- `nasm` (required to build `OpenSSL` on Windows)

To build the wheel in your local environment, clone the repository and run

```
pip wheel . --verbose
```

from the root of the source directory.
