# Ancillary files for two-loop QED $l^+l^-\to\gamma\gamma$

This repository contains the analytic results and numerical resources accompanying the calculation of the two-loop QED amplitudes for $l^+l^-\to\gamma\gamma$ and the corresponding unpolarized differential cross section.

The results use
\[
m=\frac{m_e}{\sqrt{s}},\qquad T=m^2-\frac{t}{s},\qquad U=1-T.
\]

## File descriptions

### `Hkn/Hkn.l`

The hard amplitudes, with `l = 0, 1, 2` corresponding to the Born, one-loop, and two-loop contributions, respectively. The amplitudes are stored as expansions
\[
\mathrm{H}_k=\sum_{n=0}^{12}\mathrm{H}_{k,n+1}m^n,
\qquad k=1,\ldots,8,
\]
in the form of nested lists indexed by the amplitude index $k$ and the expansion index $n$.

Only the two-loop file (`l = 2`) contains classical polylogarithms, whose arguments depend on $T$. The flags `nf` and `Lbl` identify the vacuum-polarization and light-by-light contributions, respectively.

### `Glk`

The matrix constructed from the tensor structures used to extract the invariant amplitudes.

### `W2V`

The combination
\[
\mathcal{W}(\omega_0)+2\operatorname{Re}\mathcal{V}
\]
entering the differential cross section.

### `deltas/`

This directory contains the contributions to the unpolarized differential cross section:

- `Born`: the Born contribution;
- `delta1`: the one-loop contribution;
- `delta2`: the two-loop contribution.

All three files have the same format and store the results as lists of the coefficients of $m^n$.

### `anc/Hn/Hnsmallqq.l`

The hard amplitudes from Fadin et al. (`fadin2023two` in the manuscript), with `l = 0, 1, 2`. These files are supplied as input for the numerical comparison with the results of this work.

### `CSEvaluation.nb`

A Mathematica notebook for:

- evaluating the hard amplitudes;
- constructing the unpolarized differential cross section;
- reproducing the plots presented in the paper;
- performing the numerical comparison with the hard amplitudes from Fadin et al.
