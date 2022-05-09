# overreact-workshop

Transition state search and microkinetic simulations: a workshop on using
overreact.

## Idea

```
R -> TS -> P
```

## Optimizing reactants

```
! xTB2 Opt NumFreq

*xyzfile -1 1 init.xyz
```

## Relaxed scans

Useful when you only know the reactants.

## Nudged elastic band

Useful when you have a good guess on the products (and possibly a not-that-good
idea on the TS).

```
! xTB2 NEB-TS NumFreq IRC

*xyzfile -1 1 init.xyz

%neb
 # neb_ts_xyzfile "guess.xyz"
 neb_end_xyzfile "final.xyz"

 nimages 9
end
```

We'll also need optimized products.
