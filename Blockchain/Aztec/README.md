# Aztec

There are a few products made by Aztec. The main one is [Aztec Network](https://aztec.network/), an Ethereum zk-rollup which puts a focus on privacy. One can download the aztec sandbox, which is a local env for the Aztec Network. They also have developed [Noir](https://noir-lang.org/)

## Noir

From the website :

> Noir is a Domain Specific Language for SNARK proving systems. It has been designed to use any ACIR compatible proving system. Its design choices are influenced heavily by Rust and focuses on a simple, familiar syntax.

Noir borrows many of the Rust concepts, starting with the package manager `nargo` (akin to `cargo`) and the command used to update it, `noirup` (akin to `rustup`). For now, I'll use Rust's syntax highlighting for Noir snippets (i.e. ` ```rust ` in markdown files), since they're so similar. 

Here's an example noir file (named `main.nr`) :

```rust 
fn main(x : Field, y : pub Field) {
    assert(x != y);
}
```

### Proof generation

Noir can be used to geneate a zkp of a statement. Running `nargo prove` creates the necessary files. 

### Proof verification

Of course, proofs can be verified. For that, nargo currently comes with a command to generate a Solidity verifier smart contract : `nargo codegen-verifier`.


I asked in the Aztec office hours if an effort was currently being made to create a Cairo verifier generator code, and not that we know of. This is an area I'm particularly interested in.

#### [Barretenberg](https://github.com/AztecProtocol/aztec-packages/tree/master/barretenberg)
This seems to be where the solidity codegen code lives, the solidity gen scripts are written in C++ and can be read [here](https://github.com/AztecProtocol/aztec-packages/tree/master/barretenberg/cpp/src/barretenberg/solidity_helpers/utils). The goal is to document and understand its inner workings, as well as write a version of it in Cairo. There is also the [verification key files](https://github.com/AztecProtocol/barretenberg/blob/b0d6b6c2a4259da58db400dfd4bbac0b54e87380/cpp/src/barretenberg/plonk/proof_system/verification_key/sol_gen.hpp) worth looking at.
