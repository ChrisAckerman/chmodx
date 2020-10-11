# chmodx

A cross platform command line utility for setting the executable bits on files. It is roughly equivalent to the Linux `chmod +x <patterns...>` command.

This utility was created to address the Yarn limitation where "bin" entries in `package.json` are not made executable on `yarn link`. However, it can be used any time you need to make files executable in a cross platform context.

When a file cannot be accessed:

- An error message is printed.
- The process _continues_ in order to handle all remaining files.
- The process exits with a non-zero status.

## Usage

Set the executable bit on files matching glob patterns.

```sh
npx chmodx "foo/*.js" "bar/*.js"
```

Set the executable bit on all files referenced by your `package.json' file "bin" entry. _The value(s) must be plain file paths (e.g. "src/index.js")._

```sh
npx chmodx --package
```
