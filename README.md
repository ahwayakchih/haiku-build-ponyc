# Haiku builds of Pony compiler

This repository is for building and packaging [Pony](https://www.ponylang.io/) language compiler on [Haiku](https://www.haiku-os.org/)  operating system.

To get the source code of Pony compiler, see:
https://github.com/ponylang/ponyc

To check the source code that adds support for Haiku to the Pony compiler, see:
https://github.com/ahwayakchih/ponyc/tree/haiku

**WARNING:** Sources of haiku version are rebased with almost every change, so do not depend on them or any state of them.
             That may change if they are accepted upstream at some point in future, but for now be prepared to reset local repository often.

## Package version numbers

Packages are named like this:

```
ponyc-0.70.0-1-hrev60069-x86_64.zip
```

If we split this name where `-` are and ignore file extension, we'll get:

- `ponyc`: this part is obvious ;P,
- `0.70.0`: points to ponyc's version number, but we're often building updates between ponyc releases, so ponyc version number in this case means something along the lines of "built from source for version 0.70.0 with changes towards next version applied",
- `1`: means that it's a first build for that version number, next update or re-build will have `-2` number, next will be `-3`, etc... until next ponyc version release, when it goes back to `-1`,
- `hrev60069`: means that it's a package for Haiku nightly version hrev60069 (or above). `r1beta6` will mean that it's a package for Haiku beta6 LTS release,
- `x86_64`: means that it's a package for 64-bit x86 CPUs,

If package is build with statically linked LLVM (which means it does not depend on LLVM installed in the Haiku system), it will also have `-static` part in its name, just before file extension.
