# BitCoin Nodes


## Personanl state
Currently **will not run a private node** for 

a) **no time** for setup and maintenance
b) most probably I have **not enough Internet Upload-Bandwith**
c) do not want to have **costs without a ROI**
d) do not want to became a **target for hackers**


Currently the only reason FOR a node is for getting a deeper technical understanding for how things work. 


## Overview
A full Bitcoin-node **is a "Bitcoin core"-named software that fully validates, accepts and forwards BTC transactions and blocks**. 

A node may **serve lightweight clients** transmitting their transactions to the network and by notifying them when a transaction affects their wallet. 

If not enough nodes, clients cannot connect through the network and will have to use centralized services instead.


## Bitcoin Core
Bitcoin Core checks each block of transactions it receives to ensure that everything in that block is fully valid—allowing it to trust the block without trusting the miner who created it.

This prevents miners from tricking Bitcoin Core users into accepting blocks that violate the 21 million bitcoin limit or which break other important rules.

## Benefits 
Bitcoin Core users get:

1. Better **security** by means of a built in ongoing local and remotely shared [ValidationProcessing](../Validation/_ValidationProcess.md)

2. **Privacy features** not available in other wallets

3. User **interfaces and other powerful features**

### Validation
Bitcoin Core provides the best possible security against dishonest miners along with additional security against other easier attacks by a so called [Validation Process](../Validation/_ValidationProcess.md).

## Costs And Warnings
Running a Bitcoin full node comes with certain costs and can expose you to certain risks.

### Special Cases
**This document does not cover those precautions — it only describes running a full node** to help support the Bitcoin network.

Please seek out assistance in the community if you need help setting up your full node correctly to handle high-value and privacy-sensitive tasks. Do your own diligence to ensure who you get help from is ethical, reputable and qualified to assist you. However you must take the same precautions you would when using any Bitcoin wallet. Please see the securing your wallet page for more information.

## Minimum Requirements
If you run a node on weak hardware you’ll likely spend more time dealing with issues.

PC or Desktop with 

1. Updated Windows, Mac OS X, or Linux.

2. 7 gigabytes of free disk space, accessible at a minimum read/write speed of 100 MB/s.

3. 2 gigabytes of memory (RAM)

4. A broadband Internet connection with upload speeds of at least 400 kilobits (50 kilobytes) per second

5. A connection with high upload limits. It’s common for full nodes on high-speed connections to use **200 gigabytes upload a month. Download usage is around 20 gigabytes a month**, plus around an additional 340 gigabytes the first time you start your node.

6. **6 hours a day that your full node can be left running**. (You can do other things with your computer while running a full node.) More hours would be better, and **best of all would be if you can run your node continuously**.

Note: many operating systems today (Windows, Mac, and Linux) enter a low-power mode after the screensaver activates, slowing or halting network traffic. This is often the default setting on laptops and on all Mac OS X laptops and desktops. **Check your screensaver settings and disable automatic “sleep” or “suspend” options to ensure you support the network whenever your computer is running**.

## Possible Problems
1. **Legal**: Bitcoin use is prohibited or restricted in some areas.

2. **Bandwidth limits**: Some Internet plans will charge an additional amount for any excess upload bandwidth used that isn’t included in the plan. Worse, some providers may terminate your connection without warning because of overuse. We advise that you check whether your Internet connection is subjected to such limitations and monitor your bandwidth use so that you can stop Bitcoin Core before you reach your upload limit.

3. **Anti-virus**: **Several people have placed parts of known computer viruses in the Bitcoin block chain. This block chain data can’t infect your computer, but some anti-virus programs quarantine the data anyway, making it more difficult to run Bitcoin Core. This problem mostly affects computers running Windows.**

4. **Attack target**: Bitcoin Core powers the Bitcoin peer-to-peer network, so people who want to disrupt the network may attack Bitcoin Core users in ways that will affect other things you do with your computer, such as an attack that limits your available download bandwidth.