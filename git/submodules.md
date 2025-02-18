# Submodules

## Init

```sh
git submodule update --init --recursive
```

## Update

```sh
git submodule update --recursive --remote
```

> Update the registered submodules to match what the superproject
> expects by cloning missing submodules, fetching missing commits in
> submodules and updating the working tree of the submodules.
