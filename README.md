# Blockchain with Proof of Work (PoW)

The money in cryptocurrencies (such as Bitcoin) is “produced” as the incentive for people (miners) to solve the math problems required by a particular blockchain. Since every new block has to be approved by other miners, more miners means a more secure blockchain.

If we want to make sure that only the blocks that have certain hashes can be added. For example, our blockchain may require each hash to start with 0000. The hash is calculated based on the content of the block, and it won’t start with four zeros unless someone finds an additional value to add to the block’s content to produce such a hash. Finding such a value is called block mining.

Before a new block is added to the blockchain, it is given to all nodes on the network for processing, and these nodes will start calculating the special value that produces a valid hash. The first one to find this value wins. Wins what? A blockchain may offers rewards—in the Bitcoin blockchain, a successful data miner may earn Bitcoins.

Let’s assume that our blockchain requires the hash of each block to start with 0000 (or any other number of zeros); otherwise the block will be rejected. We need to do some data mining to find a value that, if added to our block, will result in the generation of a hash that starts with 0000. We can write a program that will be adding sequential numbers (1, 2, 3, etc.) to the end of our input string until the generated hash starts with 0000. Once we know the number to include in the block’s content, so the generated hash will conform to the blockchain requirements. This number can be used just once with this particular input string. Changing any character in the input string will generate a hash that won’t start with 0000.

In cryptography, a number that can be used just once is called a nonce. We’ll add a property called nonce to the block object, and let the data miners calculate its value for each new block. A miner has to spend some computational resources to calculate the nonce, which is used as a Proof of Work (PoW), which is a must-have for any block to be considered for adding to a blockchain. 

## About the project

I create a blockchain with PoW and add blocks to it. To provide PoW it has some new propertyes, for example, nonce and a method to mine. The nonce will be concatenated to other properties of the block to produce a hash that starts with five zeros. 

The process of calculating a nonce that meets our requirements will take some time. This time, we want hashes that start with five zeros. The mine() method will invoke calculateHash() multiple times with different nonce values until the generated hash starts with 00000. 

This program run from the command line using node.js and the crypto module to generate SHA-256.

## Reference.

This project is based on "Typescript quickly" (Yakon Fain and Anton Moiseev).
