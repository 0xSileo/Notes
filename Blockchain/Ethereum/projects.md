## Consensus clients

### Lighthouse
### Teku
### Lodestar
### Nimbus
### Prysm


## Execution clients
### Geth
### Erigon
### Besu
### Reth
### Nethermind 

## L2s

The site [L2Beat](https://l2beat.com/) provides a good overview of the current L2 landscape.
### Optimistic rollups

#### Arbitrum
#### Base
#### Optimism

### zk-rollups or validity rollups
#### Starknet
#### Scroll
#### zkSync
They had launched zksync lite but it is being sunsetted. It was processing simple actions such as transfers, basic DEX fucntionality, and NFT support I think. Now the main zksync network is zkSync Era. They are a state diff zk-rollup. 
### [Eclipse](https://www.eclipse.xyz/)
They claim to be the <i>fastest</i> Ethereum L2, have to check what they mean by fast and if their claim is appropriate. They are powered by the Solana Virtual Machine.

## ZK-named things
### [ZKWASM](https://github.com/DelphinusLab/zkWasm)
It's a ZKSNARK virtual machine that supports Web Assembly. It serves as a trustless layer between rich apps running on wasm runtime and smart contracts onchain. 
It seems like WASM is assembly for the web ecosystem. Ok but what is it outside of servers and web browsers ? It's a binary instruction format for a stack-based VM. Portable compilation targed for programming languages. More info on [the WebAssembly.org website](https://webassembly.org/)

Now back to ZKWASM. From the docs : the adoption of ZKSNARK usually requires implementing a program in arithmetic circuits or circuit-friendly languages (Pinocchio, TinyRAM, Buffet/Pequin, Geppetto, xJsnark framework, ZoKrates) that forms a barrier for existing programs to leverage its power. <b>An alternative approach is, instead of applying ZKSNARK on the source code, applying it on the bytecode level of a virtual machine and implementing a zksnark-backed virtual machine.</b> In this work, we take the approach of writing the whole WASM virtual machine in ZKSNARK circuits so that existing WASM applications can benefit from ZKSNARK by simply running on the ZKWASM, without any modification. Therefore, the cloud service provider can prove to any user that the computation result is computed honestly and no private information is leaked.


### zkVMs and zkEVM
Now that we have an intuition of what zkVMs are in general, let's dive deeper and, more specifically, let's focus on zkEVMs.
The difference between the two has been explained amazingly well by David Wong [on his blog](https://www.cryptologie.net/article/564/what-are-zkvms-and-whats-the-difference-with-a-zkevm/). From the article :

> A zk VM, is simply a VM implemented as a circuit for a zero-knowledge proof (zkp) system. So, instead of proving the execution of a program, as one would normally do in zkp systems, you prove the execution of a VM. As such, some people say that non-VM zkps are part of the FPGA approach, while zkVMs are part of the CPU approach. 
> [...]
> This is essentially what a zkVM is; a zk circuit that runs a VM.


#### List of zkVMs

- [Cairo](https://www.cairo-lang.org/cairo-whitepaper/) of course, mainly used for Starknet.
- [Miden](https://polygon.technology/polygon-miden) by Polygon. 
- [RISC0](https://www.risczero.com/) applies ZK to RISCV. Yorzian [made a video](https://www.twitch.tv/videos/2087102729) talking about RISC-V and the different CPU architectures.  

#### skSVMs :
Solana also has a VM, and [some projects are creating zkSVMs](https://twitter.com/fede_intern/status/1766838023260443133). Apparently Eclipse is doing it with RISC-0. 




#### zkEVMs
The zkEVMs can be categorized in a few different types. Those were mainly defined in [Vitalik's post](https://vitalik.eth.limo/general/2022/08/04/zkevm.html) about the topic. And a good exercise is to classify the existing zkEVMs in those types. There was an effort made by the Kakarot team to explore the different existing zkEVMs. This can be a good starting point and forking the code to update it is a good project idea.
- [Kakarot](https://www.kakarot.org/) zkEVM written in Cairo.


# Questions
General place for questions related to the above projects. These should try to be answered and this doc should be updated accordingly. New questions will arise, and 
- How does zkwasm compare with Cairo ? I believe the former is specific to the web, and Cairo is more general-purpose, as [its paper](https://eprint.iacr.org/2021/1063) states that it's a <i>Turing-complete STARK-friendly CPU architecture</i>. Tbh I think those are different things because ZKWASM is applied to a VM and Cairo applies to a CPU. Is a CPU a real VM ? I guess so because it has a specific instructionset.
- Could we then have a ZKASM system ? Or so apply the principles of ZKWASM on any VM, making any VM zk-compatible ? I guess so, and I beleive that's what's done with the different ZKEVMS, which is nuts.
- Starkcet : why do I have to make a tx on <i>eth mainnet</i> and not a testnet ? Was I wrong when I wrote this ? 



