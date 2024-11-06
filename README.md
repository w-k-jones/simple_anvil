## A simple model for anvil cloud divergence and decay:

Consider an anvil of depth $D$, centred on a convective core with radius $r_0$. Assuming that the airmass is incompressible, the net, vertical convective mass flux at the base of the anvil, $\mathcal{M}_c$ must equal the horizontal mass flux that is diverged throughout the anvil, $\mathcal{M}_a$. Using this approximation, we can calculate the radial velocity, $v_r$ at any radius $r$ using the surface area of the wall of a cylinder with radius $r$ and depth $d$ as follows:

```math
\mathcal{M}_c = \rho w \pi r_0^2 = \mathcal{M}_a
\implies v_r = \frac{\mathcal{M}_a}{\rho 2 \pi r D} = \frac{w r_0^2}{2 D} \frac{1}{r}
```

As expected, the radial velocity decreases with radius to conserve the net divergence.

The age of the anvil at any specific radius can then be calculated by integrated the inverse of the radial velocity between $r_0$ and $r$:

```math
t_r = \frac{2 D}{w r_o^2} \int_{r_0}^{r} r' \, dr' = \frac{D}{w r_o^2} \left( r^2 - r_0^2 \right)
```

If we consider that in the core the cloud has an initial condensate concentration, $q_0$, that then decays over time, we can calucalte the expected condesate path, $q_r\,D$ at any radius, providing a value for the anvil "thickness". We can experiment with different decay profiles to test how this affects the anvil structure. Here, we test two, a linear decay and an exponential decay:

```math
\mathrm{Linear\ decay:}\ q_r = q_0(1 - \alpha t_r), 0 \le \alpha t_r \le 1
```

```math
\mathrm{Exponential\ decay:}\ q_r = q_0 exp^{-\alpha t_r}
```

Using these decay rates, we can calculate the area for which the condensate path is greater than some arbitrary amount, $a$. First, for linear decay:

$$ q_r = q_0 \left( 1 - \frac{\alpha D}{w r_0^2} \left(r^2 - r_0^2 \right) \right) $$

$$ q_0 D \left( 1 - \frac{\alpha D}{w r_0^2} \left(r^2 - r_0^2 \right) \right) - a = 0 $$

$$ A_a = \pi r_a^2 = \pi \left( r_0^2 - \frac{w r_0^2}{\alpha D} \left( \frac{a}{q_0 D} - 1 \right) \right) 
= \pi \frac{w r_0^2}{\alpha D} \left( 1 + \frac{\alpha D}{w} - \frac{a}{q_0 D} \right)$$

$a / q_0 d$ appears as a factor showing that the threshold can be expressed as a fraction of the initial condensate. This also holds true for optical thickness.

If we have two thresholds for thick and thin anvil, $a$ and $b$ respectively, we can calculate the thin anvil fraction of the total anvil as $1 - A_a / A_b$:

$$\mathcal{F} = 1 - \frac{1 + \frac{\alpha D}{w} - \frac{a}{q_0 D}}{1 + \frac{\alpha D}{w} - \frac{b}{q_0 D}}$$

Of immediate interest is that the radius of the core, $r_0$, has no effect on the thin anvil fraction. $D$, $\alpha$ and $w$ remain in the fraction, and while increasing $D$ or $alpha$ will decrease the difference between the thick and thin area, increasing $w$ will increase the area.

---

For exponential decay:

$$ q_r = q_0 \, exp^{- \frac{\alpha D}{w r_0^2} \left( r^2 - r_0^2 \right)} $$

$$ q_0 D exp^{- \frac{\alpha D}{w r_0^2} \left( r^2 - r_0^2 \right)} - a = 0 $$

$$ A_a = \pi r_a^2 = \pi \left( r_0^2 - \frac{w r_0^2}{\alpha D} \ln{\frac{a}{q_0 D}} \right) 
= \pi \left( \frac{\alpha D}{w} - \ln{\frac{a}{q_0 D}} \right)$$

The thin anvil fraction can be caluclated for two thresholds as:

$$\mathcal{F} = 1 - \frac{\frac{\alpha D}{w} -  \ln{\frac{a}{q_0 D}}}{\frac{\alpha D}{w} -  \ln{\frac{b}{q_0 D}}}$$

Again, $r_0$ is not present, but $w$, $D$ and $\alpha$ all affect the fraction. This behaviour may occur for any continuous function, as changing $r_0$ scales the entire system proportionately, resulting in the same area fractions

---

In the notebooks we will explore these functions and the effect of different thresholds a bit more, as well as seeing how the fraction changes over a system lifetime that is not in a steady state.
