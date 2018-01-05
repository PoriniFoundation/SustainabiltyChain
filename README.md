# SustainabiltyChain
#Tutorial to run a node

1) If you are on Windows 10 Install Linux Ubuntu using https://docs.microsoft.com/en-us/windows/wsl/install-win10
------------------------------------------
2) Install Ethereum on your Ubuntu. In your Ubuntu-Shell type each of these lines

sudo apt-get update

sudo apt-get install software-properties-common

sudo add-apt-repository -y ppa:ethereum/ethereum

sudo apt-get update

sudo apt-get install -y ethereum

git clone https://github.com/ScenicSwisscoast/SustainabiltyChain
------------------------------------------
3) initialise geth and fire up a node with bootnote "enode://f8079ec77a20affd47d0739b80b599654d4956e1fab2332a4868ea68abdf42c948fb9d0ebe28c5c2ab63ca6a65f945c37cf3acb520125e06489c9d6a06f1fc4d@52.59.201.140:30304"

sudo geth --port 30304 --rpc --rpcaddr 127.0.0.1 --rpcport 8101 --rpccorsdomain http://127.0.0.1:8000  --datadir myDataDir --networkid 19720502  init ./SustainabiltyChain/files/myGenesis.json console 2>> myEth2.log  


sudo geth --port 30304 --rpc --rpcaddr 127.0.0.1 --rpcport 8101 --rpccorsdomain http://127.0.0.1:8000  --datadir myDataDir --networkid 19720502 --bootnodes="enode://7c2905988a4de8198b9e88901f06afb54bc983b9e671c867bf6dd96a2f1a83b3809515effc951af524205a316474f63f367f4a44c9e43eecd154ed7589516a84@52.59.201.140:30304" console 2>> myEth2.log




The output should look a bit like this:

Welcome to the Geth JavaScript console!

instance: Geth/v1.7.3-stable-4bb3c89d/darwin-amd64/go1.8.3
coinbase: 0xae13d41d66af28380c7af6d825ab557eb271ffff
at block: 5 (Thu, 07 Dec 2017 17:08:48 PST)
datadir: /Users/test/my-eth-chain/myDataDir
modules: admin:1.0 clique:1.0 debug:1.0 eth:1.0 miner:1.0 net:1.0 personal:1.0 rpc:1.0 txpool:1.0 web3:1.0
>

make sure to connect MANUALLY ADD PEER
>admin.addPeer("enode://7c2905988a4de8198b9e88901f06afb54bc983b9e671c867bf6dd96a2f1a83b3809515effc951af524205a316474f63f367f4a44c9e43eecd154ed7589516a84@52.59.201.140:30304")



------------------------------------------
4) Check if you are connected to the SustainabilityChain by typing admin.peers
you should get something like this


to make sure you are syncing type 
>eth.syncing 

you should get a 
true
as a response


when you are sure that you have synced the blockchain you can go to step 5)

------------------------------------------
5)start minining
>miner.start()
------------------------------------------
6) check connections type net after the >
>net

The out put should look a bit like this 
{
  listening: true,
  peerCount: 1,
  version: "19720502",
  getListening: function(callback),
  getPeerCount: function(callback),
  getVersion: function(callback)
}






