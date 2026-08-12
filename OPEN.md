# Open questions

The square-tail inequality is closed on the natural range

```text
r >= 2,    2 <= t <= r.
```

The adjacent stripe `t=1` is not open: it is false, and it is characterized
exactly on `4<=r<=3000` — failure set exactly `[6,41]`, minimum at `r=13`,
strictly increasing recovery from `r=42` (`A45_t1_stripe.py`). The upper cells
in the natural range are not open either: they have explicit formulas and
ratios at least 2.

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
carries the ideas, and the slack it leaves is uniform and explicit: `rho >= 1`
has strict margin `1.4576%` everywhere except at `(129,2)`.

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

**Reflected zero mode and terminal positivity.** A structural sequel is tracked
in [issue #1](https://github.com/toxic2040/odd-cycles-square-tail-replay/issues/1).
It keeps the exact finite-dimensional Gram and Green identities separate from
the open all-order positivity transport. None of those follow-up claims is part
of the v0.1.0 replay.

**Formalization.** Formalizing the manuscript in Lean is unfinished. That is an
implementation frontier rather than an uncertainty in the theorem proved here.
