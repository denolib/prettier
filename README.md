# prettier

[![GitHub Actions status](https://github.com/denolib/prettier/workflows/CI/badge.svg?branch=master)](https://github.com/denolib/prettier/actions)

Prettier APIs and tools for deno.

This originally part of Deno standard modules. Moved here since `dprint` is now default
for `deno fmt`.

## Use as a CLI

To formats the source files, run:

```bash
deno --allow-read --allow-write https://denolib.com/denolib/prettier/main.ts
```

You can format only specific files by passing the arguments.

```bash
deno --allow-read --allow-write https://denolib.com/denolib/prettier/main.ts path/to/script.ts
```

You can format files on specific directory by passing the directory's path.

```bash
deno --allow-read --allow-write https://denolib.com/denolib/prettier/main.ts path/to/script.ts
```

You can format the input plain text stream. default parse it as typescript code.

```bash
cat path/to/script.ts | deno https://denolib.com/denolib/prettier/main.ts
cat path/to/script.js | deno https://denolib.com/denolib/prettier/main.ts --stdin-parser=babel
cat path/to/config.json | deno https://denolib.com/denolib/prettier/main.ts --stdin-parser=json
cat path/to/README.md | deno https://denolib.com/denolib/prettier/main.ts --stdin-parser=markdown
```

## Use API

You can use APIs of prettier as the following:

```ts
import {
  prettier,
  prettierPlugins
} from "https://denolib.com/denolib/prettier/prettier.ts";

prettier.format("const x = 1", {
  parser: "babel",
  plugins: prettierPlugins
}); // => "const x = 1;"
```
