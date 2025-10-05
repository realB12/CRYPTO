# Proof of Work (PoW)

* [Mining](../M/Mining.md)
* [Nonce](../N/Nonce.md)
* [Target](../T/Target.md)

## Abstract Visualisation
A good way to describe [Mining](../M/Mining.md) is like a giant competitive game of sudoku that resets every time someone finds a solution and whose difficulty automatically adjusts so, that it takes approximately 10 minutes to find a solution. 

Imagine a giant sudoku puzzle, several thousand rows and columns in size. If I show you a completed puzzle you can verify it quite quickly. However, if the puzzle has a few squares filled and the rest are empty, it takes a lot of work to solve! The difficulty of the sudoku can be adjusted by changing its size (more or fewer rows and columns), but it can still be verified quite easily even if it is very large. **The "puzzle" used in bitcoin is based on a cryptographic hash and exhibits similar characteristics: it is asymmetrically hard to solve but easy to verify, and its difficulty can be adjusted**.

A miner runs a mining farm that runs thousands of specialized mining computers, competing for the reward. Every 10 minutes or so, Jing’s mining computers compete against thousands of similar systems in a global race to find a solution to a block of transactions. Finding such a solution, the so-called [Proof-of-Work (PoW)](../P/PoW.md), requires quadrillions of hashing operations per second across the entire bitcoin network. The algorithm for Proof-of-Work involves repeatedly hashing the header of the block and a random number with the SHA256 cryptographic algorithm until a solution matching a predetermined pattern emerges. The first miner to find such a solution wins the round of competition and publishes that block into the blockchain.

Jing started mining in 2010 using a very fast desktop computer to find a suitable Proof-of-Work for new blocks. As more miners started joining the bitcoin network, the difficulty of the problem increased rapidly. Soon, Jing and other miners upgraded to more specialized hardware, such as high-end dedicated graphical processing units (GPUs) cards such as those used in gaming desktops or consoles. At the time of this writing, the difficulty is so high that it is profitable only to mine with application-specific integrated circuits (ASIC), essentially hundreds of mining algorithms printed in hardware, running in parallel on a single silicon chip. Jing’s company also participates in a mining pool, which much like a lottery pool allows several participants to share their efforts and rewards. Jing’s company now runs a warehouse containing thousands of ASIC miners to mine for bitcoin 24 hours a day. The company pays its electricity costs by selling the bitcoin it is able to generate from mining, creating some income from the profits.

## Bitcoin Technology
Bei Bitcoin besteht der Proof of Work im Wesentlichen darin, eine Variable im [Block Header](../B/Block%20Header.md) - die sogenannte [Nonce](../N/Nonce.md) so lange zu variieren, biss der [Hashwert für diesen Block](../B/Block%20Hash.md) kleiner als eine bestimmte Zahl - das sogenannte [Target](../T/Target.md) wird. Diese TargetZahl wird nach 2016 generierten Blöcken immer so weit angepasst, dass in etwa alle 10 Minuten ein neuer Block generiert werden kann. 



