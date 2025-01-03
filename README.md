# Snippets
Snippets collection for a set of different programming languages.

The only goal is to have one community driven repository for all kinds of
snippets in all programming languages, this way you can have it all in one
place.

## Install

Use your plugin manager of choice, e.g.

### With Lazy.nvim

```lua
{ "kevinm6/snippets" }
```

<details>
<summary><b>Neovim (native)</b></summary>

> ⚠️ 
> Requirements:    
>  - **nvim** >= 0.10  
>  - [nvim-snippets](https://github.com/garymjr/nvim-snippets)  
>  - **nvim** commit [f1775da](https://github.com/neovim/neovim/commit/f1775da07fe48da629468bcfcc2a8a6c4c3f40ed)  
> ```lua
> -- Example config
> {
>   "garymjr/nvim-snippets",
>   event = "InsertEnter",
>   dependencies = { "kevinm6/snippets" },
   >   opts = function(_, o)
>     o.extended_filetypes = {
>       javascript = { "jsdoc" },
>       lua = { "luadoc" },
>       java = { "javadoc", "java-testing" },
>       quarto = { "markdown" },
>    }
>
>    o.search_paths = { vim.fn.stdpath "data" .. "/lazy/snippets"  }
>   end
> }
> ```

</details>

<details>
<summary><b>LuaSnip</b></summary>

> ⚠️ WARNING  
> If you're using **LuaSnip** make sure to use  
> `require("luasnip.loaders.from_vscode").lazy_load()`, and add
> `snippets` as a dependency for LuaSnip, otherwise snippets might not
> be detected. If you don't use `lazy_load()` you might notice a slower
> startup-time
>
> ```lua
> {
>   "L3MON4D3/LuaSnip",
>   dependencies = { "kevinm6/snippets" },
> }
> ```

</details>

---

### With Packer

```lua
use "kevinm6/snippets"
```

---

### With vim-plug

```vim
Plug "kevinm6/snippets"
```

---

### With coc.nvim

```vim
:CocInstall https://github.com/kevinm6/snippets@main
```

## Usage

This collection of snippets should work with any snippet engine that supports
loading vscode snippets. Like for example:

- [vim.snippet](https://github.com/neovim/neovim/pull/25301)
- [vim-vsnip](https://github.com/hrsh7th/vim-vsnip)
- [LuaSnip](https://github.com/L3MON4D3/LuaSnip)
- [coc-snippets](https://github.com/neoclide/coc-snippets)

## Add snippets from a framework to a filetype.

> [!NOTE]
> This is handled by your snippet engine and has nothing to do with this snippets collection

There's extra snippets included in this repo but they are not added by default,
since it would be irrelevant for people not using those frameworks. See
[`snippets/frameworks`](https://github.com/kevinm6/snippets/tree/main/snippets/frameworks)

For example: if you want to add rails snippets to ruby.

With LuaSnip:

```lua
require'luasnip'.filetype_extend("ruby", {"rails"})
```

With vim-vsnip:

```viml
let g:vsnip_filetypes.ruby = ['rails']
```

## Excluding snippets

> [!NOTE]
> This is handled by your snippet engine and has nothing to do with this snippets collection

With LuaSnip, see `help luasnip-loaders`

```lua
-- Lazy
-- https://github.com/folke/lazy.nvim
{
  "hrsh7th/nvim-cmp",
  event = "InsertEnter",
  dependencies = {
    -- set as dependencies to be loaded when nvim-cmp is loaded
    "kevinm6/snippets"
    -- "hrsh7th/cmp-nvim-lsp",
    -- "hrsh7th/cmp-buffer",
  },
}

-- Packer
use "kevinm6/snippets"

-- Plug
Plug "kevinm6/snippets"
```

#### With Lazy.nvim

**PLEASE NOTE:** If you're using [Lazy](https://github.com/folke/lazy.nvim), you must add ```friendly-snippets``` as an nvim-cmp dependency, otherwise it may be loaded after other plugins. See [this issue](https://github.com/rafamadriz/friendly-snippets/issues/239#issue-1553567010) and [this issue](https://github.com/folke/lazy.nvim/issues/266#issuecomment-1368271202) for more information. As an example:

```lua

return {
  'hrsh7th/cmp-nvim-lsp',
  dependencies = {
	  'kevinm6/snippets',
	  'L3MON4D3/LuaSnip',
  },
  config = function()
    -- the rest of your configuration
  end
}
```

## Showcase

### HTML

![HTML gif](https://user-images.githubusercontent.com/67771985/131255337-d53f3408-b60d-44a2-93ba-9a3240a7436e.gif)

### JS

![JS gif](https://user-images.githubusercontent.com/67771985/131255342-e393165a-e4b1-401e-9084-a782b9dd3fef.gif)

## TODO

- Add all included snippets to the
  [Wiki](https://github.com/rafamadriz/friendly-snippets/wiki).

## Thanks to all contributors

<a href="https://github.com/kevinm6/snippets/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=rafamadriz/friendly-snippets" />
</a>

## Credits

A good portion of the snippets have been forked from the following repositories:

- [friendly-snippets](https://github.com/rafamadriz/friendly-snippets)
- [vscode-standardjs-snippets](https://github.com/capaj/vscode-standardjs-snippets)
- [python-snippets](https://github.com/cstrap/python-snippets)
- [vs-snippets](https://github.com/kitagry/vs-snippets)
- [Wscats/html-snippets](https://github.com/Wscats/html-snippets)
- [Harry-Ross/vscode-c-snippets](https://github.com/Harry-Ross/vscode-c-snippets)
- [vscode-jekyll-snippets](https://github.com/edheltzel/vscode-jekyll-snippets)
- [vscode-fortran-support](https://github.com/krvajal/vscode-fortran-support)
- [vscode_cobol](https://github.com/spgennard/vscode_cobol)
- [VSCode-LaTeX-Snippets](https://github.com/JeffersonQin/VSCode-LaTeX-Snippets)
- [vscode-react-javascript-snippets](https://github.com/dsznajder/vscode-react-javascript-snippets)
- [honza/vim-snippets - Verilog](https://github.com/honza/vim-snippets/blob/master/snippets/verilog.snippets)
- [vscode-relm4-snippets](https://github.com/Relm4/vscode-relm4-snippets)
- And more...
