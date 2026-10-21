# GBGRegistry

The Julia package registry of the GBG packages: GBGCodingTools and the science
packages built with it. Each final release is recorded here, so a package is
installed by name and moves only between releases.

## Installing a package

```julia
using Pkg
Pkg.Registry.add("General")
Pkg.Registry.add(url = "https://github.com/GrigorySarnitsky/GBGRegistry")
Pkg.add("GBGPeriodicFields")
```

`General` is added first because, on a fresh Julia, adding this registry alone
leaves `General` out, and every dependency outside these packages is there.

## What is here

`Registry.toml` lists the packages. Each has a folder under its first letter,
`G/<Name>/`, the layout of Julia's General registry: `Package.toml` (name, uuid,
repository), `Versions.toml` (each version's git tree hash), `Deps.toml` and
`Compat.toml`.

## How it is kept

Only `gbg release` writes here: it records a package's final release after
tagging it. Nothing is edited by hand.
