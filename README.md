# solc-builds

The main purpose of the repo is to provide MacOS aarch64 binaries for [roynalnaruto/svm-rs](https://github.com/roynalnaruto/svm-rs) and eventually for [gakonst/foundry](https://github.com/gakonst/foundry).

### Pre-requisite

[`Z3`](https://github.com/Z3Prover/z3) is required to build `solc` with SMT solver support.

* Download `Z3` (version `4.8.17` should be compatible with `solidity >= 0.8.15`) and unzip
```
$ wget https://github.com/Z3Prover/z3/releases/download/z3-4.8.17/z3-4.8.17-arm64-osx-10.16.zip
$ unzip z3-4.8.17-arm64-osx-10.16.zip && cd z3-4.8.17-arm64-osx-10.16
```
* Copy to `/usr/local`
```
$ cp bin/libz3.a /usr/local/lib
$ cp bin/z3 /usr/local/bin
$ cp include/* /usr/local/include
```

### Build Instructions

The following steps are meant to be run on a MacOS machine with the M1 chip:

* Clone the [solidity](https://github.com/ethereum/solidity) repository
* Checkout to the release tag of interest:
```
$ git checkout tags/v0.8.15
```
* Build the `solc` binary for the above release tag
```
$ ./scripts/build.sh
```
* The binary `solc` is then found under the `./build/solc/` directory
* Get the SHA-256 checksum for the binary
```
$ shasum -a 256 ./build/solc/solc
```
