# Starknet  

Starknet is a validity rollup launched by StarkWare. It has native account abstraction, and its own virtual machine called the Cairo VM.


## Proving


### Stwo

The [Stwo](https://starkware.co/stwo-prover-the-next-gen-of-stark-scaling-is-here/) prover is a new iteration, making use of circle STARKS. 


### Circle STARKS

This new type of STARKS is an improvement over the previous systems used. This protocol is defined over the Mersenne prime field M31, and is a collaboration betweenPolygon Labs ([Ulrich Haböck](https://x.com/UHaboeck)) and StarkWare ([Shahar Papini](https://x.com/papinishahar) & David Levit). The paper has been published [on the IACR website](https://eprint.iacr.org/2024/278).


## Bitcoin 
On June 4th 2024, Eli Ben-Sasson published a [blog post](https://starkware.co/scaling-bitcoin-for-mass-use/) about making use of the OP_CAT opcode in [Bitcoin script](https://en.bitcoin.it/wiki/Script), if it ever sees the light of day. He argues that within six months of its adoption, Starknet could settle on Bitcoin and Ethereum simultaneously. Indeed, their prover [Stwo](#stwo) works on the M31 finite field, which plays nicely with Bitcoin script. 




## Resources 

- [Cairo whitepaper](https://eprint.iacr.org/2021/1063.pdf)
