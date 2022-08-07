# solc-builds

The main purpose of the repo is to provide MacOS aarch64 binaries for [roynalnaruto/svm-rs](https://github.com/roynalnaruto/svm-rs) and eventually for [gakonst/foundry](https://github.com/gakonst/foundry).

### Pre-requisite

[`Z3`](https://github.com/Z3Prover/z3) is required to build `solc` with SMT solver support.

Different `solc` versions depend on different versions of `Z3`.

* Get the commit for the appropriate `Z3` version from [here](https://github.com/Homebrew/homebrew-core/commits/5d6ac395090c6635b634feb6e7fa92a5fd4a1886/Formula/z3.rb).
* Get the corresponding formula code (`z3.rb` file). For instance, for `z3 v4.8.17` [here](https://github.com/Homebrew/homebrew-core/blob/841cde393531a6239af9ce4771e2c8027dda0664/Formula/z3.rb) is the formula.
* Download the formula
```
$ wget https://raw.githubusercontent.com/Homebrew/homebrew-core/841cde393531a6239af9ce4771e2c8027dda0664/Formula/z3.rb
```
* Install `Z3`
```
$ brew unlink z3
$ brew install z3.rb
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
