# $Presence Token Technical Documentation

## Overview
The $Presence token is a specialized ERC-20 token that implements a continuous decay mechanism to represent physical presence at a land Project. Unlike standard ERC-20 tokens, $Presence tokens automatically decrease in value over time, creating a time-weighted representation of community participation where recent stays have higher value than older ones.


## Core Features

*Non-transferrable*: Tokens can only be minted and burned, not transferred between addresses
*Continuous Decay*: Token balances automatically decay at a configurable daily rate
*Time-Weighted Governance*: Recent presence has higher weight than historical presence
*Role-Based Access Control*: Only authorized roles can mint and burn tokens

## Technical Implementation
The $Presence token extends OpenZeppelin's ERC20Upgradeable contract with additional functionality for decay management:

```
soliditycontract PresenceToken is ERC20Upgradeable, Ownable2StepUpgradeable {
    // Core functionality and state variables
}
```

## Decay Mechanism
The decay mechanism calculates token value reduction over time based on a configurable daily decay rate:

Decay Rate: Configurable parameter that determines how quickly tokens lose value
Last Decay Timestamp: Tracks when each address's balance was last updated
Last Decayed Balance: Stores the previously calculated decayed balance

Balance calculations follow this pattern:

balanceOf(address) returns the decay-adjusted balance at current time
When tokens are minted or burned, the last decayed balance is recalculated first

Token Decay Formula
The decay follows an exponential decay formula:
decayedAmount = initialAmount * (1 - decayRatePerDay)^numberOfDays
Where:

*initialAmount* is the original token amount
*decayRatePerDay* is the daily decay rate (configurable)
*numberOfDays* is the number of days since the last update

## Minting
Tokens are minted when Citizens stay in the project:

`solidityfunction mint(address account, uint256 amount, uint256 daysAgo) external`

Parameters:
*account*: Address of the Citizen
*amount*: Number of tokens to mint
*daysAgo*: If minting for a past stay, days since the stay occurred

## Burning
Tokens can be burned if a Citizen's stay is canceled or for other adjustments:

`solidityfunction burn(address account, BurnData[] calldata burnDataArray) external returns (uint256 finalBalance)`

Parameters:
*account*: Address of the Citizen
*burnDataArray*: Array of burn amounts and corresponding daysAgo values

## Access Control
Access to mint and burn functions is restricted to addresses with the following roles:

BOOKING_PLATFORM_ROLE
BOOKING_MANAGER_ROLE
Contract owner (typically a Multisig)

## Integration with Governance
The $Presence token is designed to integrate with a governance system. When used in governance, the decayed balance of $Presence tokens give greater voting influence to Citizens with recent physical presence.

_Example 1: Token Decay_
If a Citizen receives 1 $Presence token and the daily decay rate is 0.03% (approximately 10% per year):

After 30 days: ~0.99 tokens remain
After 180 days: ~0.95 tokens remain
After 365 days: ~0.90 tokens remain

_Example 2: Multiple Minting Events_
If a Citizen:

Receives 1 $Presence token
Waits 60 days (token decays to ~0.98)
Receives another 1 $Presence token
Total balance becomes ~1.98 tokens
After another 30 days, balance decays to ~1.96 tokens

## Limitations and Considerations

- Token transfers are explicitly prohibited
- Token approvals are disabled
- High-precision math is used to prevent rounding errors during decay calculations
- Small rounding errors (up to 100,000 wei) are tolerated during burn operations
- 
## Deployment
$Presence tokens are deployed as part of the token ecosystem for each project. The contract uses the Upgradeable Proxy pattern from OpenZeppelin to allow for future functionality improvements while preserving token balances.