# Debian package for [LibreSSL](http://www.libressl.org)

This repository provides the LibreSSL alternative to OpenSSL packaged for Debian.

## Packages

It currently provides four packages, similar to the OpenSSL packages in Debian:
* `libressl-utils`: the `/usr/bin/openssl` and such, conflicts with the Debian `openssl` package.
* `libressl-doc`: development documentation
* `libressl2.3`: LibreSSL libraries `libssl.so`, `libtls.so` and `libcrypto.so`. Libary versions should differ to the OpenSSL ones, thus should be possible to co-exist with e.g. `libssl1.0.0`.
* `libressl-dev`: Development files, conflicts with the Debian `openssl-dev` package.

## Building

This repository should build LibreSSL simply by cloning it and building it, preferably with [pbuilder](https://wiki.ubuntu.com/PbuilderHowto).

If you have setup a pbuilder environment, build the package by running `pdebuild` in the cloned repository.

## Using LibreSSL

In order for applications to use LibreSSL instead, they need to be re-linked against LibreSSL instead of OpenSSL.
Many times, it is as simple as changing dependencies from `libssl-dev` to `libressl-dev` and rebuild the package.

It might be useful to rebuild packages inside a [pbuilder](https://wiki.ubuntu.com/PbuilderHowto) environment to avoid conflicts with `libssl-dev`.
