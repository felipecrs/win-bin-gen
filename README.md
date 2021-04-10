# win-bin-gen

**This is a very WIP, and I don't even know if it will get released at all.**

This generates Windows shims which calls the `cli.js` using `node.exe`, without using `cmd.exe` and thus not failing to run under UNC (such as WSL) paths.

The `contrib\shim.exe` is was generated using the code from `https://github.com/kiennq/scoop-better-shimexe/pull/1`.

The goal is to be give package maintainers the ability of generating Windows shims better than the ones generated by NPM using `cmd.exe`. The planned workflow is:

1. `npm install --save-dev win-bin-gen` in the package with bins
2. Add `win-bin-gen` to the `prepare` script in the `package.json`, so it will run every time someone runs `npm install` when developing the project.
3. Make sure the generated shim is included in the `npm` package that gets distributed.
