# Using lspconfig

## Keybinds to remember
* 'gri' - go to implementation
* 'grd' - go to definition
* 'gra' - gives actions on current diagnostic
* ']d/e/w' - next diagnostic/error/warning
* '[d/e/w' - previous diagnostic/error/warning
* '<C-w d>' - show diagnostic message under cursor

## Formatting
Formatting can be controlled using .editorconfig files for most, though some language servers require their own kind of config (ie. clang needs .clang_config).

Formatting can be run at any time via the command `:lua vim.lsp.buf.format()`.

Formatting can be set to run automatically on save via the following:
```lua
vim.api.nvim_create_autocmd('LspAttach', {
	callback = function(args)
		local client = vim.lsp.get_client_by_id(args.data.client_id)
		if not client then return end

		if client.supports_method('textDocument/formatting') then
			-- format the buffer on save
			vim.api.nvim_create_autocmd('BufWritePre', {
				buffer = args.buf,
				callback = function()
					vim.lsp.buf.format({ bufnr = args.buf, id = client.id })
				end,
			})
		end
	end,
})
```
