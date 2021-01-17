---
---

# Blockchain and Market Making Presentation

---

## How does Blockchain Work
- Everybody should've watched the video!!!

1. As a precursor everybody watch the 3 Blue 1 Brown Video video before the group meeting:
	1. https://www.youtube.com/watch?v=bBC-nXj3Ng4
2. make brief slide or two explaining over process and allow anyone to ask questions

## People

Miners- adding blocks to transaction history
Full nodes- people who store a complete copy of the blockchain and is able to verify all transactions since the beginning. You don't get any money from running a full node.
- However, it increases the security of transactions conducted by the one runnig the node. This is especially important if you plan to conduct multiple bitcoin transactions in a day. It also contributes to the overall security of bitcoin’s network. Also, by downloading all transactions, a full node will always have the latest and greatest information relating to information on bitcoin’s blockchain. It will help them monitor the health of bitcoin’s blockchain: The blockchain has a direct bearing on bitcoin’s price since it is used to process transactions—both commercial or trading-related.

## Storing Bitcoin
- Private key only you know -> generates public address for you to receive bitcoin
- Hot Wallet
	- Online wallets are also known as “hot” wallets. Hot wallets are wallets that run on internet-connected devices like computers, phones, or tablets.
	- these wallets generate the [private keys](https://web.archive.org/web/20201002065830/https://www.investopedia.com/terms/p/private-key.asp) to your coins on these internet-connected devices, so hypothetically they can be accessed by somebody
	- If you have your account on coinbase, robinhood, etc. then you're holding through their online wallet with their own private key, you don't have your own.
- Cold wallet
	- local on your device
	- some people print their private keys and don't store them on their computer
	- Many people accessing old wallets with lost private keys

## Transactions
https://developer.bitcoin.org/devguide/contracts.html
- Bitcoin arbitration (escrow): https://www.bitrated.com
	- 3rd party to sign transaction
- Microtransactions
	- what if you have a few micro transactions are the amount of transaction fees?
	- You can real time update on a contract to the network a bunch of incremental payments every time a service is performanced and then actually send the total of payments at the end of the day
- Anonymity
	- She knows every transaction gets added to the public block chain, so when Bob and Charlie pay her, they can each easily track those satoshis to learn what Bitcoin addresses she pays, how much she pays them, and possibly how many satoshis she has left.
	- **Coinjoin** takes a bunch of peoples bitcoins together and collectively agree to transfer satoshis between each other so no one besides them can reliably determine who controls which satoshis.

Bitcoin purchases are discrete. Unless a user voluntarily publishes his Bitcoin transactions, his purchases are never associated with his personal identity, much like cash-only purchases, and cannot easily be traced back to him. In fact, the anonymous bitcoin address that is generated for user purchases changes with each transaction

## Mining Hardware
While the hardware used by miners is broadly of three types: CPU/GPU (Graphical Processing Units), FPGA (Field Programmable Gate Array) and ASIC (Application Specific Integrated Circuits),
- But the introduction of [application specific integrated circuit](https://www.investopedia.com/articles/investing/121814/popular-bitcoin-mining-software.asp) chips (ASIC) offered up to 100 billion times the capability of older personal machines, rendering the use of personal computing to mine bitcoins inefficient and obsolete
- You can **Cloud Mine** if you want
- Hosted mining is the most popular form of cloud mining. In this model, the customer purchases or leases mining hardware located in a miner's facility. The miner is responsible for maintaining the equipment and ensuring that it functions as performed. Through this model, customers have direct control over their cryptocurrency.

## Hash Attack
- Amount that miners can mine is enforced so that the amount of bitcoin given out is constant
- If I'm a miner why wouldn't I just come in and mine a lot when the the rate of mining is low which drives up the hash rate, making the algorithm increase the difficulty to mine a block
- For Bitcoin the difficulty is adjusted every 2016 blocks (every 2 weeks approximately) so that the average time between each block remains 10 minutes.
- Other coins use smaller time scales and numbers of blocks to adjust on (smaller time scales mean you can have more transactions cause you have more blocks)
- But if you have more blocks the people running the full nodes need a proportional amount of memory to store the info from each block


## What are different variations of the algorithm
- **proof-of-work** They need to find a specific value for a variable that will produce a HASH beginning with zeros. If your system requires a minimum of 40 zeros in each validated transaction, the miner will need to calculate approximately 2^40 different HASH values in order to find the right **proof-of-work**
- Etherium switched algorithm from proof of work to proof of stake
	- In a distributed consensus-based on the proof of Work, miners need a lot of energy. One Bitcoin transaction required the same amount of electricity as powering [1.57 American households](https://blockgeeks.com/bitcoins-energy-consumption/) for one day [(data from 2015](https://blockgeeks.com/bitcoins-energy-consumption/)). In recent research, experts argued that [bitcoin transactions](https://blockgeeks.com/bitcoin-transactions/) may consume as much electricity as Denmark by 2020.
	- roof of stake will make the entire mining process virtual and replace miners with validators. This is how the process will work:
	- The validators will have to lock up some of their coins as a stake.
	- After that, they will start validating the blocks. Meaning, when they discover a block that they think can be added to the chain, they will validate it by placing a bet on it.
	- If the block gets appended, then the validators will get a reward proportional to their bets.
- A bunch of other ones depending on the method (called consensus algorithms)

## Wallets with the most bitcoin
- chart with who is holding bitcoin over time (I think it was from maybe ARK invest and it was of people with >10k bitcoin over time)
- Countries are holding a lot
- CIA is holding a lot

## Times when Bitcoin Wallets/Exchanegs were Hacked
- 

## Different cryptocurrencies and their use cases
- Etherium
	- buying cryptokitties
	- buying travis scott paintings
	- Robbie on SuperRare
- non-fungible _token_ (_NFT_)
	- https://rarible.com
	- https://godsunchained.com
		- like hearthstone but a lot of real money
- https://www.maecenas.co
- Ripple (XRP)
	- Payments
- Tether (USDT)
- Bitcoin Cash: The debate which led to the creation of BCH had to do with the issue of scalability; the Bitcoin network has a strict limit on the size of blocks: one megabyte (MB). BCH increases the block size from one MB to eight MB, with the idea being that larger blocks will allow for faster transaction times.
- Stellar lumens
- STORJ
- https://www.stateofthedapps.com

## What happens when 21 million run out
- The bitcoin halving
	- The first rule of the Bitcoin system is that there can be a maximum of 21,000,000 Bitcoins generated. This number has still not been achieved, and according to current trends, it is thought that this number will be reached by the year 2140.
	- The first 18.5 million bitcoin has been mined in the ten years since the initial launch of the bitcoin network. With only three million more coins to go, it might appear like we are in the final stages of bitcoin mining.
	- Transaction fee may mean that bitcoin miners still mine after they expire
- Miners return is way higher
- Options in bitcoin
- Bitcoin credit cards (my dad is getting one)
- companies are buying bitcoin

## Transition Into How Does a Market Work
- picture of me holding up my driver's license for binance
- I wanna trade my bitcoin/also works for stocks

## Show Bid and Ask Price Plot
- walk through how it works and how the price you see reported on robinhood is usually the avg of the bid and ask

## There are 2 types of orders
- limit order
- market order

## Why can I execute trade right away
- market makers like Virtu can arbitrage by placing orders on both sides of market
- also they are paid by exchanges to provide liquidity (meaning they are paid to put their limit orders)

## Why is robinhood trading free
- If you place limit order you are being paid to place your order by exchange, so you get to place it for free on robinhood
- if you place market order, they sell that order to the market makers:
	- in return marker makers get an order crossing the spread as well as information quicker than anyone else what direcation the order is coming from

