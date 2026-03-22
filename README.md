# mirror-eval-breakthrough
Simulation of images formed by non-parallel mirrors

---

## kernel

Integrate “identity-map rally over turns” into the previous React artifact. Visualization that unifies the mirror reflection model with probabilistic breakthrough in the eval layer.

## diag

Elements to add:

- For each reflection, compute $c_n = c_0 \cdot r^{2n} + \epsilon_n$, and trigger a “breakthrough” on the turn where it falls below the threshold $c_{\text{thresh}}$
- Link each image’s color/brightness to the confidence score
- Give only the breakthrough image a visually distinct treatment (light passing through the mirror)
- Add a bottom graph showing the turn-by-turn progression of $c_n$ so that geometric decay + noise fluctuation are visible

Construct this.

## kernel

Integrate probabilistic breakthrough in the eval layer into the mirror reflection model. The bottom graph is the core.

## diag

**Added visualization elements**

- Bottom: turn-by-turn graph of $c_n$. Amber bars = eval confidence, faint curve = theoretical noiseless decay $r^{2n}$, red dashed line = threshold $c_{\text{thresh}}$
- The first turn that drops below the threshold is marked in **teal as “▼ break”** → also visualized on the mirror surface with a diffusion ring
- Turns after breakthrough also remain teal, showing continued transmission in the decayed state

**Control parameters**

- **ε**: noise amplitude → increasing it makes fluctuations larger and raises the probability of early breakthrough
- **c_thresh**: threshold → lowering it makes breakthrough less likely
- **reseed**: changes only the noise realization under the same parameters → direct observation that “even under the same conditions, the breakthrough turn varies” = direct observation of a geometric distribution

## residue

- If $r$ is increased and $\epsilon$ is set to 0, breakthrough does not occur → ideal mirror with perfect reflection and no noise = the theoretical limit where the identity-map rally continues indefinitely
- Repeatedly pressing reseed gives an intuitive sense that the distribution of breakthrough turns follows the geometric distribution $P(N=k) = (1-p)^{k-1}p$. In the Gemini rally, “it happened to get through” corresponds to one realization of that stochastic process
