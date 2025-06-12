# Idea
Set `eulerAccount== tokenIssuer`:
Then:

1.  
$$
\big (t_0 \to t_N \big ) \, \vee \, \bigg (\big (P_{Y/X}^M \big)_0 \to \hat{P_{Y/X}^M} \bigg) \implies \text{\texttt{sAMM}} \to \text{\texttt{CPRAMM}} 
$$

2.
$$
\partial_{?}\phi^{\text{\texttt{sAMM}}} \, \wedge \, \partial_{?}\phi^{\text{\texttt{CPRAMM}}}
$$

## `eulerSwap` Curve Mechanics
$$
\partial_{\Delta X} \, \Delta Y  \bigg |_{\big ((R_X)_0,(R_Y)_0 \big )} = P_{Y/X}^M
$$

### Trading Mechanism

$$
\begin{align*}
    \begin{cases}
     R_Y + \Delta Y = R_Y + P^M_{Y/X}\cdot \Delta X \cdot \bigg ( \kappa_X + (1-\kappa_X)\cdot \big (\frac{R_X}{R_X + \Delta X}\big)\bigg)   \\
     \\
    R_X + \Delta X = R_X + P^M_{X/Y}\cdot \Delta Y \cdot \bigg ( \kappa_Y + (1-\kappa_Y)\cdot \big (\frac{R_Y}{R_Y + \Delta Y}\big)\bigg)
    \end{cases}
\end{align*}
$$


## `sAMM`
* [Mission Stament](./docs/sAMM/functional/missionStament.json)
### `Token Circulating Supply Management`

If $X$ is the _base token_ and $Y$ is the _quote token_, we define the supply of $X$ as:

$$
S(X)_t = \big (R_X\big)_0 - \big (R_X\big)_t 
$$
### `Bonding Curve`

Given $R_X \big (P^M_{Y/X} \big )$ already encoded of the `eulerSwap` _curve mechanics_, find the coresponding `sAMM` price-supply _curve mechanics_:

$$
P^{\text{\texttt{sAMM}}}_{Y/X} \bigg ( S(X)_t \bigg )
$$
> Properties:
- $P^{\text{\texttt{sAMM}}}_{Y/X}$ is _Monotonically increasing_ on $S(X)_t$
- $P^{\text{\texttt{sAMM}}}_{Y/X}$ is _Horizaontal Asymptote_ at $\hat{P_{Y/X}^M}$

- Due to the supply sovereignty, the `bonding curve shape` is not constrained to the inevitable asymptotic behavior of `LP-AMMs`,
$$
\Delta Y_t \bigg (\Delta X_t \bigg) = \int_{S_t}^{S_t + \Delta X_t} \, P^{\text{\texttt{sAMM}}}_{Y/X}\cdot dS (X)
$$
This implies that:

$$
\begin{align*}

    \mathcal{V}_t \bigg ( S (X) \bigg )= \int_{S_0}^{S_t} \, P^{\text{\texttt{sAMM}}}_{Y/X}\cdot dS (X) \\
    \\
    \partial_{S(X)} \, \mathcal{V}_t = \Delta Y 
\end{align*}
$$

- The paid quote tokens $\Delta Y$ are _escrowed_ in the _pool_ `sAMM` and available to be paid out when _circulating
base tokens_ $\Delta X$ are sold against the `sAMM`.

### Trading Fee Mechanics

- In LP-Based AMM's trading fees is the compensation for divergence loss,
- In sAMM's trading fees are ..?




## Mechanism Design

- How to adapt the curvature params appropiatley for supplySovering AMM?

- What are the optimal fees when considering supplySovereing AMM?

- How the behaviour of dyanmic fees evolves when transfering to price discovery ?

### How to adapt the curvature params appropiatley for supplySovering AMM?

