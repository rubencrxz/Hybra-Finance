# 🐉 Hybra-Finance

Hybra Finance is a DeFi protocol on Hyperliquid EVM that combines a concentrated-liquidity AMM (a Uniswap v3–style CL pool system) with an upgraded ve(3,3) governance and emissions engine. 
At its core, HYBR is the base ERC-20 token whose emissions are scheduled and minted through an upgradeable minter, creating a weekly incentive budget that feeds the system. 
Users can lock HYBR into a vote-escrow contract to mint veHYBR NFTs, where voting power decays with time and can be managed via extensions, merges, splits, and delegation. 
Those veNFT votes are then routed through the voter layer to assign gauge weights per epoch, deciding which pools and liquidity positions receive HYBR emissions. 
On the liquidity side, the CLFactory deploys CLPool instances that run the concentrated-liquidity swap logic and generate real trading fees, which act as the protocol’s economic “fuel.” 
Swap costs can be made adaptive via a DynamicSwapFeeModule that derives a volatility component from the pool’s tick vs a TWAP-like observation window, shaping fees per market conditions. 
Gauges (both classic and CL-NFT oriented) distribute emissions and route fee/bribe flows, so LPs earn from both trading fees and voted incentives while partners can add bribes to attract liquidity. 
Finally, RewardHYBR and related modules handle how claimed emissions are represented and converted (e.g., toward liquid HYBR or long-term aligned positions), closing the flywheel that links fees → votes → emissions → liquidity → fees.
