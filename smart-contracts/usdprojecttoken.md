# $ProjectToken

The $ProjectToken (i.e. $TDF), is a simple fungible ERC20 token.



Parameters:

* Total Supply (totalSupply): May be tied to total number of nights available each year in the Project.
* Liquid Supply (saleHardCap): Number of tokens sold in current sale.
* Transfer limitations: Only allow transfer after calling Diamond contract and validating transfer (which would be enabled after GoLive & only for tokens that aren’t locked for a booking)
* Decimals: 18
* isTransferrable: DAO defined flag
