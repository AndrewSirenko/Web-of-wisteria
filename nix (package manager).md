### Sources
- [Zero to nix](https://zero-to-nix.com/start/install)
- [Some notes on using nix](https://jvns.ca/blog/2023/02/28/some-notes-on-using-nix/)

### Install

easy nix installer from [1. Get Nix running on your system](https://zero-to-nix.com/start/install)
```
curl --proto '=https' --tlsv1.2 -sSf -L https://install.determinate.systems/nix | sh -s -- install
```

Open new terminal session and verify `nix` was added to `$PATH` with `nix --version`

### Run a program with nix


```
echo "Hello Nix" | nix run "nixpkgs#figlet"
```

Note: "The first time you run a program using nix run it's likely to be a slow operation. That's because Nix needs to build the program's package from scratch—or download it from a known cache—and store it in the Nix store. This is in contrast to most package managers, which install things more quickly because they download pre-built archives like tarballs. Future nix run invocations should be instantaneous, as Nix doesn't need to build the package again." - [2. Run a program with Nix](https://zero-to-nix.com/start/nix-run)

- It used the nixpkgs flake reference to pull in some Nix code and targeted the figlet flake output.
- It built the figlet package and stored the result in the Nix store.
- It ran the executable at bin/figlet from the figlet package.

In Nix, every program is part of a package. Packages are built using the Nix language. The figlet package has a single program (also called figlet) but packages can contain multiple programs as well as man pages, configuration files, and more. The ffmpeg package, for example, provides both ffmpeg and ffprobe.
- [2. Run a program with Nix](https://zero-to-nix.com/start/nix-run)

### TODO Development Environments (Docker replacement)

[3. Explore Nix development environments](https://zero-to-nix.com/start/nix-develop)

Specifically the language-specific environments

### TODO Build packages

[4. Build a package using Nix](https://zero-to-nix.com/start/nix-build)

### TODO Declarative Package Management

