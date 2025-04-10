---
description: 'Status: Draft, Last Updated: 8 June 2024'
---

# Decay

The Decay function periodically reduces the balance of all token holders by a specified decay rate. This rate can be set as a percentage of the token holder's balance and is executed at predetermined intervals. The decay mechanism can be implemented as an automated process within the token's smart contract, ensuring consistent and transparent operations.

ℹ _The decay is applied to $Presence & $Sweat. Eac_

**Key Components**

1. **Decay Rate**:
   * The Decay rate is the percentage of the token balance that will be reduced periodically.
   * Example: A 1% decay rate would mean that each token holder's balance is reduced by 1% at each interval.
2. **Decay Interval**:
   * The interval at which the decay function is executed.
   * Example: The decay function could be executed daily, weekly, or monthly.
3. **Trigger Mechanism**:
   * The decay function can be triggered automatically using blockchain events or manually by a designated authority or smart contract function.
4. **Exemptions**:
   * Specific accounts or smart contract addresses (such as staking contracts or liquidity pools) can be exempted from the decay function.

<pre><code><strong>// Sample code (GPT)
</strong><strong>function applyDecay() external {
</strong>    uint256 decayRate = 1; // Decay rate in percentage
    uint256 totalSupply = totalSupply();
    for (uint256 i = 0; i &#x3C; holders.length; i++) {
        address holder = holders[i];
        uint256 balance = balanceOf(holder);
        uint256 decayAmount = balance.mul(decayRate).div(100);
        _burn(holder, decayAmount);
    }
    emit DecayApplied(totalSupply, decayRate);
}
</code></pre>
