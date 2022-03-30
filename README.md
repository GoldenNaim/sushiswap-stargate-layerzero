# Summary

This contract allow everyone to swap on **sushiswap** and to send the result to another chain by using **LayerZero** and **Stargate** in one transaction.


This contract has been deployed on multiple network, listed above :
Network  | Address
------------- | -------------
Ethereum  | 0x000000
Polygon | https://polygonscan.com/address/0x4aAFcE8f89Ba11fD555a3d2A910Bd2FDB2465282
BSC | https://bscscan.com/address/0xDA5468bF65e42a8C7bA0a3df93e5f622A5E1fcd9
Avalanche | 0x000000
Fantom | https://ftmscan.com/address/0xDA5468bF65e42a8C7bA0a3df93e5f622A5E1fcd9

# Functions 

### swapThenSend

This function must be used if you want to swap **an ERC20 token** against USDC, USDT, BUSD ( on BSC ) or STG.
The parameters are listed above : 

Parameters | Value
------------- | -------------
amount *(uint256)* | The quantity that you want to swap
route  *(address[])* | The route used on sushiswap 
minAmount *(uint256)* | The minimum you want to receive
chainID *(uint16)* | The recipient chainID 
srcPoolID *(uint256)* | The pool ID used on the current network
dstPoolID *(uint256)* | The pool ID used on the recipient network
target *(address)* | The recipient address
slippageStargate *(uint256)* | The maximum slippage in percentage 


**chainID, srcPoolID and dstPoolID** can be found here : https://stargateprotocol.gitbook.io/stargate/developers/contract-addresses/mainnet

### swapNativeThenSend

This function must be used if you want to swap **a native token ( Ethereum, Matic..)** against USDC, USDT, BUSD ( on BSC ) or STG.

The parameters are listed above : 

Parameters | Value
------------- | -------------
amount *(uint256)* | The quantity that you want to swap
route  *(address[])* | The route used on sushiswap 
minAmount *(uint256)* | The minimum you want to receive
chainID *(uint16)* | The recipient chainID 
srcPoolID *(uint256)* | The pool ID used on the current network
dstPoolID *(uint256)* | The pool ID used on the recipient network
target *(address)* | The recipient address
slippageStargate *(uint256)* | The maximum slippage in percentage 


**chainID, srcPoolID and dstPoolID** can be found here : https://stargateprotocol.gitbook.io/stargate/developers/contract-addresses/mainnet

### inCaseIf

Because we are never careful enough, if someone send tokens directly to the contract, the owner has the possibility to send them back by using this function.

Parameters | Value
------------- | -------------
mode *(uint256)* | The mode ( 1: ERC20 token - 2: Native token )
token  *(address[])* | The token to send ( put 0x0000000000000000000000000000000000000001 for native token )
amount *(uint256)* | The quantity to send
recipient *(address)* | Recipient address

# Links

sushiswap : https://app.sushi.com/

layerZero : https://layerzero.network/

stargate : https://stargate.finance/

# Author

https://twitter.com/BrutalTrade
