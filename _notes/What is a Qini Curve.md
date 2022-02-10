---
title: What is a Qini Curve
tree_state: 🌱
---

The Qini Curve is the Cumulative ITE on the treated
- The area is the area between this curve and the random uplift curve which is just a straight line from (0,0) to the rightmost point of your Qini Curve
$$\text { Qini Curve Area }=\sum_{i=0}^{M-1} \frac{1}{2}\left(\frac{n_{t, y=1}\left(\phi_{i+1}\right)-n_{t, y=1}\left(\phi_{i}\right)}{N_{t}}-\frac{n_{c, y=1}\left(\phi_{i+1}\right)-n_{c, y=1}\left(\phi_{i}\right)}{N_{c}}\right) \frac{1}{M}$$

where $\phi_i = i/M$.

$$\text { Qini Curve Area }=\sum_{i=0}^{M-1} \frac{1}{2}\left(\operatorname{Qini} \operatorname{curve}\left(\phi_{i+1}\right)+\operatorname{Qini} \operatorname{curve}\left(\phi_{i}\right)\right)\left(\phi_{i+1}-\phi_{i}\right)$$

$$\text { Randomized Qini Area }= \frac{1}{2}(\operatorname{Qini} \operatorname{curve}(\phi_{M}))$$

$$Q = \text { Qini Curve Area } - \text { Randomized Qini Area }$$

$$f(t)=\left(\frac{Y_{t}^{T}}{N_{t}^{T}}-\frac{Y_{t}^{C}}{N_{t}^{C}}\right)\left(N_{t}^{T}+N_{t}^{C}\right)$$

$$g(t)=Y_{t}^{T}-\frac{Y_{t}^{C} N_{t}^{T}}{N_{t}^{C}}$$

for the $t$ datapoints sorted by largest predicted ITE/Uplift, We calculate 


- I think it is just cumulative ITE in order of decreasing predicted ITEs 



Qini curve plots the cumulative uplift across the population. We rank the customers by their predicted uplift on the horizontal axis, and the vertical axis plots the cumulative number of purchases in the treatment group (scaled by the total treatment size) minus the cumulative number of purchases in control (scaled by the total control size).

https://www.ambiata.com/blog/2020-07-07-uplift-modeling/