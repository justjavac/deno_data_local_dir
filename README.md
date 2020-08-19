# deno_data_local_dir

[![tag](https://img.shields.io/github/release/justjavac/deno_data_local_dir)](https://github.com/justjavac/deno_data_local_dir/releases)
[![Build Status](https://github.com/justjavac/deno_data_local_dir/workflows/ci/badge.svg?branch=master)](https://github.com/justjavac/deno_data_local_dir/actions)
[![license](https://img.shields.io/github/license/justjavac/deno_data_local_dir)](https://github.com/justjavac/deno_data_local_dir/blob/master/LICENSE)

> _In v1.1.2(2020.06.26), Deno [Remove `Deno.dir` and dirs dependency #6385](https://github.com/denoland/deno/pull/6385)_

Returns the path to the user's local data directory.

The returned value depends on the operating system and is either a string,
containing a value from the following table, or `null`.

|Platform | Value                                    | Example                                      |
| ------- | ---------------------------------------- | -------------------------------------------- |
| Linux   | `$XDG_DATA_HOME` or `$HOME`/.local/share | /home/justjavac/.local/share                 |
| macOS   | `$HOME`/Library/Application Support      | /Users/justjavac/Library/Application Support |
| Windows | `{FOLDERID_LocalAppData}`                | C:\Users\justjavac\AppData\Local             |

## Usage

Requires `allow-env` permission.

Returns `null` if there is no applicable directory or if any other error occurs.

```ts
import dataLocalDir from "https://deno.land/x/data_local_dir/mod.ts";

dataLocalDir();
// Lin: "/home/justjavac/.local/share"
// Mac: "/Users/justjavac/Library/Application Support"
// Win: "C:\Users\justjavac\AppData\Local"
```

## License

[deno_data_local_dir](https://github.com/justjavac/deno_data_local_dir) is released under the MIT License. See the bundled [LICENSE](./LICENSE) file for details.
