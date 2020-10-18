# My Vim Workflow
This is how I do things in Vim.

## Neovim
Firstly, I dont actually use Vim, I use Neovim. The original reason was that at the time that I chose to learn Vim in college, the Hacker News/Reddit hype machine directed me towards Neovim instead. 

Now, I actually do use it over Vim purposefully for 2 main reasons

1. The integrated :terminal
2. The built-in LSP client

## Finding Files
`,ff` Opens the fuzzy file finder, which is how I navigate around to different files the majority of the time

For finding files that I know are close to the file I'm currently working on, `,j` will open netrw inside of the active dir.

## Searching Across Project
`,e` Will open Grepper, which uses `rg` to do a grep-style search in the active directory
<todo: Figure how to put word under curosr into Grepper automatically>

## Find and Replace Across Project
<todo>

## Language Features/"Intellisense"/IDE-Like Features

I used to use a combination of `deoplete` and `ale` for completion and linting/typechecking, but things always seemed to conflict and break without much direction as to how to fix it.

Then I moved to `coc.nvim`, which advertises itself as a kind of a "drop in" replacement for all of the IDE-like functionality you expect from VSCode. You install coc.nvim, and then a bunch of extensions like `coc-tsserver` and `coc-json`, and then completion, linting, fixing, etc. mostly just starts working (maybe with some configuration in the separate coc-settings.json file.) The issue I had with coc was that it was often very slow, and more often showed very out-of-date or just broken diagnostics (e.g. diagnostics like "Cannot find symbol myVarararariableee", or valid diagnostics that were fixed minutes ago, and show as fixed after a `:e!`). It's also fairly heavy, with a lot of different concepts like CocLists and CocActions and CocCommands, that I honestly just never wanted to bother wrapping my head around. Not really blaming coc for that, but I was looking for something with a little less abstraction.

Now, I use the built-in Language Server Protocol client in Neovim for diagnostics and completion, and Ale for linting and fixing. Setting up the LSP client has a more complicated setup process than Coc, but is much lighter and easier to wrap my head around once set up. 

- `https://github.com/neovim/nvim-lspconfig` This plugin just makes setting up the LSP a little (a lot) easier
- `https://github.com/nvim-lua/completion-nvim` This plugin improves the completion experience for LSP
- `https://github.com/nvim-lua/diagnostics-nvim` This plugin improves the diagnostics experience for LSP

Various links with some helpful words:
https://www.reddit.com/r/neovim/comments/h0ndj0/to_those_who_have_integrated_lsp_functionality/
https://www.reddit.com/r/neovim/comments/igyj1f/neovim_lsp_is_really_awesome/
https://nathansmith.io/posts/neovim-lsp
`:h lsp` is also very helpful
