# EtherMinerUbuntu

## Setup an Google VM instance or EC2 instance if you haven't yet here.
this will help you setup a node in google cloud if you would prefer instead of AWS - https://gist.github.com/cryptogoth/ee67803f66af7db095062d50b22e3a6f 

### Install ubuntu dependencies and ethereum softwares 
I have tested this on Ubuntu 16.04 LTS (Google VM instance) 
```
sudo apt-get install software-properties-common
sudo add-apt-repository -y ppa:ethereum/ethereum-qt
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo add-apt-repository ppa:ethereum/ethereum-dev
sudo apt-get update
sudo apt-get install ethereum
sudo apt-get install cpp-ethereum
```



## Setup ether wallet and Join a mining pool

To start mining, you’ll need an Ethereum wallet and to join a mining pool.

To generate a wallet, simply go to https://www.myetherwallet.com and follow the steps. By the end of the process, you’ll receieve a wallet address.

We’ll be using Dwarfpool for mining, which is rated in the top best mining pools. Feel free to use others if you like.

## Starting Miner
Simply SSH to your instance and type:
```
tmux  
ethminer -G -F http://eth-eu.dwarfpool.com/{WALLET ADDRESS}/{YOUR_EMAIL ADDRESS} --cl-local-work 256 --cl-global-work 16384
```

Tmux allows you to keep a process running after closing your SSH connection.

Ethminer is an Ethereum GPU mining worker. Entering your email address allows you to receive notifications on payouts. The other parameters are for mining optimizations.

That’s it!

You should soon see a DAG file generated and right afterward, your mining should start. To view your stats, simply go to https://dwarfpool.com/eth and in ‘Worker stats’ enter your wallet address.

For more information on Ether mining see the README of the official GitHub repository https://github.com/ethereum-mining/ethminer 
