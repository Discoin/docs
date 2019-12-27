---
description: How Discoin automatically adjusts for inflation.
---

# Dynamic rates and reserve

## Setup <a id="37ba7d35-ac82-4300-a288-82df4f9d95f7"></a>

Discoin starts with a currency called ABC with a reserve of 100.

{% hint style="info" %}
You can think of the reserve as a big bank vault where Discoin goes to get the coins when someone is exchanging currencies.
{% endhint %}

Each ABC is equivalent to 2 Discoin tokens \(𝔻$\), and vice versa.

That means the market cap of ABC is 200𝔻$.

$$
100 \space \text{ABC} \times \frac{2\mathbb{D}\$}{1 \space \text{ABC}} = 200\mathbb{D}\$
$$

## A transaction is started <a id="8996db05-1115-466e-8e42-5ccbd6e41766"></a>

A user wants to convert 10 ABC into XYZ.

Discoin has their 10 ABC added to the reserve.

$$
100 \space \text{ABC} + 10 \space \text{ABC}
$$

The Discoin reserve is now holding 110 ABC.

The market cap of all the ABC in 𝔻$ should still be 200𝔻$.

To keep the market cap at the same value we **devalue ABC**.

$$
\frac{200\mathbb{D}\$}{110 \space \text{ABC}} = \frac{1.81\mathbb{D}\$}{1 \space \text{ABC}}
$$

The new value of 1 ABC is now 1.81𝔻$.

The response from the API directs the receiving bot to payout the correct amount of XYZ. This value is derived by converting the currencies like this:

$$
10 \space \text{ABC} \rightarrow 18.1 \space \mathbb{D}\$ \rightarrow\text{XYZ}
$$

