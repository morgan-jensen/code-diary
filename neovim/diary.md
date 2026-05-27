# NeoVim Configuration Diary

## Log
**May 16 2026**:  
Started nvim configuration.

Implemented basic file structure for `~/.config/nvim`. Added file to define basic option settings.

Installed nerd fonts into terminal for future improvements.

**May 20 2026**  
Added telescope and mini.nvim to the configuration.

So far the only mini modules added are notify and fuzzy. Notify should add pop up notifications and fuzzy is an algorithm for telescope.

**May 26 2026**
Worked on adding lsp configuration. Added lsp servers for cpp (clangd) and markdown (marksman).

Marksman was compliled from the repository using the dotnet framework.
Clangd came with clang from pacman.

I also installed the html language server from vscode. It doesn't have snippets by default, so I will need a snippets plugin to get that to work.
To see how to do that see [here](https://github.com/neovim/nvim-lspconfig/blob/master/doc/configs.md#html).

To get marksman to work, I had to move the executable from its original location in `~/.local/bin` to `/usr/local/bin` `/usr/local/bin`.

I tried using mini.snippets plugin, but I feel like I like the completion that comes with vim lspconfig better.

I tried installing quick-lint-js as a javascript option, but it got messed up quick. I gave up.

I ended the night with installing the lsp for vue so that I can start the app project soon.
