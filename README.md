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
------------------------------------------
3) fire up Ethereum connecting to the SustainabilityChain type in your console

sudo geth --datadir ./myDataDir --networkid 12345  console 2>> myEth2.log

The output should look a bit like this:

Welcome to the Geth JavaScript console!

instance: Geth/v1.7.3-stable-4bb3c89d/darwin-amd64/go1.8.3
coinbase: 0xae13d41d66af28380c7af6d825ab557eb271ffff
at block: 5 (Thu, 07 Dec 2017 17:08:48 PST)
datadir: /Users/test/my-eth-chain/myDataDir
modules: admin:1.0 clique:1.0 debug:1.0 eth:1.0 miner:1.0 net:1.0 personal:1.0 rpc:1.0 txpool:1.0 web3:1.0
>

------------------------------------------
4) Connect to the SustainabilityChain: after this new console prompt > type (or copy paste everything after the >

> admin.addPeer("enode://33b2814ac9d9e5ee6c9d4e0ded8e74505387a245b642a2cb2617c3e4e57b18527806e1d74d7d995eeff1f520a4f0f098a6a36b509a599cdd0558d20cc0a26c3d@52.59.201.140:30303")
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






