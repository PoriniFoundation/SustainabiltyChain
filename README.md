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

sudo geth --datadir ./myDataDir --networkid 19720502  console 2>> myEth2.log

The output should look a bit like this:

Welcome to the Geth JavaScript console!

instance: Geth/v1.7.3-stable-4bb3c89d/darwin-amd64/go1.8.3
coinbase: 0xae13d41d66af28380c7af6d825ab557eb271ffff
at block: 5 (Thu, 07 Dec 2017 17:08:48 PST)
datadir: /Users/test/my-eth-chain/myDataDir
modules: admin:1.0 clique:1.0 debug:1.0 eth:1.0 miner:1.0 net:1.0 personal:1.0 rpc:1.0 txpool:1.0 web3:1.0
>

------------------------------------------
4) Connect to the SustainabilityChain: after these 2 new console prompts > type (or copy paste everything after the >

>admin.addPeer("enode://df764111e7dcf81e617ceb7d9aea3836edfe5a5392dbce8d88bc70cfce2472de376818181e799d4c9d78f758aa35827c642da387ccc33fa064d03a3d55300139@172.26.3.66:30303")

>admin.addPeer("enode://df764111e7dcf81e617ceb7d9aea3836edfe5a5392dbce8d88bc70cfce2472de376818181e799d4c9d78f758aa35827c642da387ccc33fa064d03a3d55300139@52.59.201.140:30303")

enode://8013e27087d9aab5caa4ccca74a9e8e2656749f2a66bc05b20e2151c57f98c1dca7d8ee618ef5c4fdf3a8e2ee80f1de3bb7709907932c75418cbe94af0545334@172.26.3.66:30301

enode://8013e27087d9aab5caa4ccca74a9e8e2656749f2a66bc05b20e2151c57f98c1dca7d8ee618ef5c4fdf3a8e2ee80f1de3bb7709907932c75418cbe94af0545334@52.59.201.140:30301

enode://f0b5c98ab443491087c1be4e5e45f583d29130216fd85b0d93f13fdeb3b5f6325e85f8414630332cb9491a4d18b6a37e530f19d0b4a183f50fa5d11c7ff23434@52.59.201.140:30303

"enode://1589e6da5760d6d79590562eadc89c0dbe9a27861a7255ecf12852c75c86bb8f7233779d291f3bfcf905d9aeeb7e05dcbe8c1440f6bbcbda0cdfdc57b1e1751c@52.59.201.140:30303"

type 
>eth.syncing

online after syncing stopped go to step 5)

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






