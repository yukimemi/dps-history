# chronicle

Denops Chronicle

# Features

chronicle is a Vim plugin that record opened files and saved files in the specified path.

# Installation

If you use [folke/lazy.nvim](https://github.com/folke/lazy.nvim).

```lua
{
  "yukimemi/chronicle.vim",
  lazy = false,
  dependencies = {
    "vim-denops/denops.vim",
  },
}
```

If you use [yukimemi/dvpm](https://github.com/yukimemi/dvpm).

```typescript
dvpm.add({ url: "yukimemi/chronicle.vim" });
```

# Requirements

- [Deno - A modern runtime for JavaScript and TypeScript](https://deno.land/)
- [vim-denops/denops.vim: 🐜 An ecosystem of Vim/Neovim which allows developers to write cross-platform plugins in Deno](https://github.com/vim-denops/denops.vim)

# Usage

No special settings are required.
By default, record the file to bellow.

- On `BufRead`.

  `g:chronicle_read_path`

- On `BufWritePost`.

  `g:chronicle_write_path`

# Commands

`:DisableChronicle`

Disable chronicle.

`:EnableChronicle`

Enable chronicle.

`:OpenChronicleRead`

Show list of `g:chronicle_read_path` with quickfix.

`:OpenChronicleWrite`

Show list of `g:chronicle_write_path` with quickfix.

`:ResetChronicleRead`

Remove `g:chronicle_read_path`.

`:ResetChronicleWrite`

Remove `g:chronicle_write_path`.

# Functions

`chronicle#read#list()`

Get list of `g:chronicle_read_path`.

`chronicle#write#list()`

Get list of `g:chronicle_write_path`.

# Config

No settings are required. However, the following settings can be made if necessary.

`g:chronicle_debug`

Enable debug messages.
default is v:false

`g:chronicle_ignore_filetypes`

A list of filetypes to be ignored.
default is ["log", "gitcommit"]

`g:chronicle_echo`

Whether to output echo messages when adding to chronicle list.
default is v:true

`g:chronicle_notify`

Whether to `vim.notify` messages when adding to chronicle list. (Neovim only)
default is v:false

`g:chronicle_read_path`

The path saved on BufRead event.
Default is `~/.chronicle/read`

`g:chronicle_write_path`

The path saved on BufWritePost event.
Default is `~/.chronicle/write`

`g:chronicle_throttle_interval`

The throttle interval miliseconds of adding to chronicle list.
default is 500

# Example

```vim
let g:chronicle_debug = v:false
let g:chronicle_echo = v:false
let g:chronicle_notify = v:true
let g:chronicle_ignore_filetypes = ["csv", "log"]
let g:chronicle_read_path = "~/.cache/chronicle/read"
let g:chronicle_write_path = "~/.cache/chronicle/write"
nnoremap mr <cmd>OpenChronicleRead<cr>
nnoremap mw <cmd>OpenChronicleWrite<cr>
```

# Integration

## [nvim-telescope/telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)

- [yukimemi/telescope-chronicle.nvim](https://github.com/yukimemi/telescope-chronicle.nvim)

## [Shougo/ddu.vim](https://github.com/Shougo/ddu.vim)

- [yukimemi/ddu-source-chronicle: ddu.vim source of dps-chronicle](https://github.com/yukimemi/ddu-source-chronicle)

## [vim-fall/fall.vim](https://github.com/vim-fall/fall.vim) 

- [yukimemi/fall-source-chronicle: fall.vim source for chronicle.vim](https://github.com/yukimemi/fall-source-chronicle)

# Special thanks

The original idea of this plugin comes from [lambdalisue/mr.vim](https://github.com/lambdalisue/mr.vim).
Thank you!

# License

Licensed under MIT License.

Copyright (c) 2024 yukimemi

