# solc-builds

The main purpose of the repo is to provide MacOS aarch64 binaries for [roynalnaruto/svm-rs](https://github.com/roynalnaruto/svm-rs) and eventually for [gakonst/foundry](https://github.com/gakonst/foundry).

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
