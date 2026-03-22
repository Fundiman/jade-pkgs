# jade-pkgs

The official Jade package registry.  
Part of [Fundiman/JadeLang](https://github.com/Fundiman/JadeLang).

---

## publishing a package

```bash
# from your Jade project directory
python3 jpkg.py publish
```

this will:
1. fork this repo to your GitHub account
2. create a branch `pkg/<your-package>/<version>`
3. add your `jade.toml` and `out.joc`
4. open a pull request automatically

requires `git` and [gh cli](https://cli.github.com) — authenticate with `gh auth login`

## manually publishing

if you prefer to do it manually:

1. fork this repo
2. create `packages/<your>/<package>/<version>/`
3. add `jade.toml` and `out.joc`
4. update `packages/index.json`
5. open a pull request

## package structure

```
packages/
  com/
    yourname/
      mypackage/
        1.0.0/
          jade.toml    ← package metadata
          out.joc      ← compiled Jade binary (multi-arch)
  jade/
    stdlib/            ← official standard library
      ...
  index.json           ← registry index
```

## installing packages

```bash
python3 jpkg.py add com.yourname.mypackage
python3 jpkg.py install
```

## license

packages are licensed by their authors.  
the registry infrastructure is LGPL-3.0.
