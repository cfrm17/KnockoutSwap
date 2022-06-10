# Knockout Swap

A BMA Knockout swap is a two-legged BMA ratio swap where one leg pays a contract specified fixed rate and the other leg pays Libor times a contract specified ratio plus a contract specified constant spread. 

On any contract payment date both the fixed and Libor coupon payments may cancel if the historical average BMA rate observed during the coupon period is above (or below, as specified by the contract) the knockout strike. For example, consider a contract where one party receives the fixed rate and pays 68% of 1M Libor. Both payments are cancelled if on a coupon date the 1M average of the 1W observations of the BMA rate (i.e., the average of the prior 4 observations of 1W BMA rate) is greater 5%.

If we consider a deal called Libor Swap with BMA Knock-In where the knockout condition is defined by a maximum level for average BMA, the coupon payments at time i S are the following:

There is a dual switch between Libor Swap with BMA Knock-In and Libor Swap with BMA Knock-Out. To avoid the tedious repetition, we only review Libor Swap with BMA Knock-Out below.

Now we want to get the payoff of the equation above. Under the forward measure T , we assume that BMA rate and Libor rate are following two different driftless Geometry Brownian Motions:

Libor Delta for each Libor curvebuild instrument perturb the market rate by 1bp, rebuild the Libor and BMA curves, then re-price the digital Libor KO deal.

The i -th Libor Delta is defined as LiborDeltai = V (the i -th Libor instrument rate + 1bp) - V (nominal)

BMA Ratio Delta for each BMA curve build market ratio perturbs the market ratio by one point, rebuild the BMA curve, and then re-price the digital Libor KO deal. The i -th BMA Ratio Delta is defined as

BMARatioDeltai = V ( the i -th BMA Ratio rate + 1%) - V (nominal)

Libor Vega Perturb all Libor vols by 1 point then re-price.

LiborVega = V (all Libor vols + 1%) - V (nominal)


References:

https://finpricing.com/lib/EqCallable.html

https://zenodo.org/record/6551223/files/MbaKnockoutSwap.pdf

https://zenodo.org/record/6551223#.YpDv2agpDq4

