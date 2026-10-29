# Open questions

The square-tail inequality is closed on the natural range

```text
r >= 2,    2 <= t <= r.
```

The adjacent stripe `t=1` lies outside that range. For the shift-wall
consequence it is not open: the reversed shift-wall ratio `omega_1(r)` is below
1 there, and the stripe is characterized exactly on `4<=r<=3000` — failure set
exactly `[6,41]`, minimum at `r=13`, strictly increasing recovery from `r=42`
(`A45_t1_stripe.py`, which evaluates the shift-wall ratio, not the square-tail
ratio). The upper cells in the natural range are not open either: they have
explicit formulas and square-tail ratios at least 2.

## The uniform constant is now determined

Earlier releases listed the exact uniform constant as the main open question.
It is closed. With

```text
rho(r,t) = r^2 d_(r,t)^2 / (2 S_(r,t)V_(r,t)),
```

the minimum of `rho` over the whole range is attained, at one cell only:

```text
min rho = rho(129,2) = 1.014576164564870742...,   attained only at (129,2).
```

Equivalently the sharp uniform constant replacing the factor 2 is

```text
C* = 2 rho(129,2) = 2.029152329129741484617172393669...,
```

an explicit rational whose reduced numerator and denominator have 1,233 digits
each. The runner-up is the neighbouring cell `(128,2)`, separated from the
minimum by `1.5878e-6`. The replayed chain is `global_infimum_tails.json`,
`global_infimum_reduction.json`, `global_infimum_windows.json`,
`core_uniqueness.json`, `dyadic_screen.json` and `global_infimum_join.json`.

The factor 2 is retained as the structural theorem. Its proof is the one that
carries the ideas, and the slack it leaves is uniform and explicit:
`rho - 1 >= rho(129,2) - 1 = 0.014576164564870742...`, with equality only at
`(129,2)`.

## The downstream shift-wall constant is also determined

The companion paper *The sharp constant in the shift-wall bridge for odd-cycle
polynomials* proves

```text
Omega_t(r) >= Omega_2(1350)  for all integers r>=t>=2,
```

with equality only at `(r,t)=(1350,2)`. Its sharp raw bridge factor is

```text
2 Omega_2(1350) = 2.655018313913361199726406175676...
```

That downstream theorem is archived at
[doi:10.5281/zenodo.21866366](https://doi.org/10.5281/zenodo.21866366), with
the public replay in
[`shift-wall-sharp-factor`](https://github.com/toxic2040/shift-wall-sharp-factor).
It does not alter the square-tail theorem or its sharp uniform constant above.

## What is still open

**Shape of the column minima away from the core.** Each fixed column `t` has an
interior minimum in `r`, and on the certified core `4 <= r <= 503` the 500
column minima increase strictly in `t`. Whether that monotonicity persists for
every `t` is not proved. Ordinary floating-point exploration suggests the
argmins grow geometrically, but nothing here bounds its error, and no such scan
is offered as evidence.

**Formalization.** Formalizing the manuscript in Lean is unfinished. That is an
implementation frontier rather than an uncertainty in the theorem proved here.

## Retracted all-order claims

[Issue #1](https://github.com/toxic2040/odd-cycles-square-tail-replay/issues/1)
was closed on 2026-08-14 following an exact counterexample. Its
[closing comment](https://github.com/toxic2040/odd-cycles-square-tail-replay/issues/1#issuecomment-5297269972)
withdraws the proposed equivalence between all-order terminal positivity and
coefficient-ratio absolute/complete monotonicity. The two conditions are not
the same class (the floor-shifted absolute-monotonicity cone is closed under
sums and products; total positivity is not), so the equivalence is not
established; no same-object counterexample to it is on record. The proposed
transport along `N(N+c)`, `tau_pin >= eta_s eta_{s-1} tau_free`, is refuted
exactly at `(n,s)=(5309,20)`, with both quantities strictly positive.

The exact finite-dimensional Gram and Green identities, including the partner
zero mode and projector identity, are unaffected and are being carried
privately; issue #1 is no longer their tracker. These follow-up results are not
part of the v0.1.0 replay.

No theorem in the four published papers changes. In particular, the published
coefficient-index total-positivity proof uses Lindström's lemma, Jacobi's
complementary-minor identity, and checkerboard sign matrices independently of
the retracted cone argument. The square-tail theorem and its sharp uniform
constant, the sharp TP2 threshold, and the sharp shift-wall constant remain
unchanged. This status correction does not modify the frozen v0.1.0 release.
