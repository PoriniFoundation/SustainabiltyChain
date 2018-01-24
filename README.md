# SustainabiltyChain
#Tutorial to run a node
#whenever it says FILL_IN_BOOTNODE_INFO replace this with everything below inclunding the " at the beginnin and the end

"enode://bc44b9322ad19113d6a4d69121c7dc91e95e2e7b9e85dae871da03dcac76a06ddd7cf5dba13d15d882596aeddcf6bf667ecf3914204b81d6b9fb9aed115f7e5e@52.59.201.140:30304"

REAL DEAL USE THIS
"enode://0fe08c0fd6643f54bfcb6987e9fa2201bf22bbabe846b565a222e85d1c93826ece52b77f30860b73838e32ac9e79946df521b2228ffe10eb38748eda1451880c@52.59.201.140:30304"

alternively try this "enode://cf2a1e3bb2cfe5a8aed058b609d6f4c844238e44425a7b24e422ce61cd971257859db2a8c4584acfe9bd65ffbec78d7db5cba14cbf32953f8f5c94e08135b20c@46.231.206.125:30304"


------------------------------------------
1) If you are on Windows 10 Install Linux Ubuntu using https://docs.microsoft.com/en-us/windows/wsl/install-win10

------------------------------------------
2) Install Ethereum on your Ubuntu. In your Ubuntu-Shell type each of these lines

sudo apt-get update

sudo apt-get install software-properties-common

sudo add-apt-repository -y ppa:ethereum/ethereum

sudo apt-get update

sudo apt-get install -y ethereum

git clone git@github.com:ScenicSwisscoast/SustainabiltyChain


------------------------------------------
3) initialise geth and fire up a node with bootnote info

sudo geth --port 30304 --rpc --rpcaddr 127.0.0.1 --rpcport 8101 --rpccorsdomain http://127.0.0.1:8000  --datadir myDataDir --networkid 19720502  init ./SustainabiltyChain/files/myGenesis72.json console 2>> myEth2.log  


sudo geth --port 30304 --rpc --rpcaddr 127.0.0.1 --rpcport 8101 --rpccorsdomain http://127.0.0.1:8000  --datadir myDataDir --networkid 19720502 --bootnodes=FILL_IN_BOOTNODE_INFO_HERE
 console 2>> myEth2.log




The output should look a bit like this:

Welcome to the Geth JavaScript console!

instance: Geth/v1.7.3-stable-4bb3c89d/darwin-amd64/go1.8.3
coinbase: 0xae13d41d66af28380c7af6d825ab557eb271ffff
at block: 5 (Thu, 07 Dec 2017 17:08:48 PST)
datadir: /Users/test/my-eth-chain/myDataDir
modules: admin:1.0 clique:1.0 debug:1.0 eth:1.0 miner:1.0 net:1.0 personal:1.0 rpc:1.0 txpool:1.0 web3:1.0
>

make sure to connect MANUALLY ADD PEER
>admin.addPeer(FILL_IN_BOOTNODE_INFO)



------------------------------------------
4) Check if you are connected to the SustainabilityChain by typing admin.peers
and somewhere you should see your BOOTNODE_INFO this whole section 4) is also featured in more detail in appendix a)

type in
>net
you should see at least one node connected


to make sure you are syncing type 
>eth.syncing 

you should get a 
false
as a response


that means it is synced already and is not syncing anymore, that is a good thing, that is what you want
when you are sure that you have synced the blockchain you can go to step 5)


------------------------------------------
5)start minining

create an account by typing
personal.newAccount("Password")

>miner.start()
check balances from time to time 
eth.getBalance(eth.coinbase)/10E18

------------------------------------------
Appendix A) check connections type net after the >
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

check if bootnode is connected
>admin.peers

result should show something like this that includes the bootsnode
[{
    caps: ["eth/63"],
    id: "f8079ec77a20affd47d0739b80b599654d4956e1fab2332a4868ea68abdf42c948fb9d0ebe28c5c2ab63ca6a65f945c37cf3acb520125e06489c9d6a06f1fc4d",
    name: "Geth/v1.7.3-stable-4bb3c89d/linux-amd64/go1.9",
    network: {
      localAddress: "192.168.1.112:33612",
      remoteAddress: "52.59.201.140:30304"
    },
    protocols: {
      eth: {
        difficulty: 91489639,
        head: "0x13da4f44cab80151071944d331389650feb4a6fe0e363a076774eafc81551fd3",
        version: 63
      }
    }
}]





