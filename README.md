# vim-vimhelplint

## How to use

1. Install **vim-vimhelplint**
    - Copy `ftplugin/help_lint.vim` to your `~/.vim/ftplugin/help_lint.vim`.
    - Or you can use your favorite plugin manager ([Vundle](https://github.com/gmarik/Vundle.vim), [Neobundle](https://github.com/Shougo/neobundle.vim), [vim-plug](https://github.com/junegunn/vim-plug)).

    ```vim
    " Vundle
    Plugin 'machakann/vim-vimhelplint'

    " Neobundle
    NeoBundle 'machakann/vim-vimhelplint'

    " vim-plug
    Plug 'machakann/vim-vimhelplint'
    ```

1. Open Vim and edit your help file: `:edit path/to/your_help_file.txt`

1. Execute the ex command `:VimhelpLint`, and it will report errors to the
   quickfix list. You can use e.g. `:copen` to open the list then.
   Use `:VimhelpLint!` to open the quickfix window automatically.

---

Or if you are using [Neomake](https://github.com/neomake/neomake), run the shell command in the root directory of Neomake plugin.

```
make build/vimhelplint
```

Then it automatically downloads vimhelplint, you can run it by:

```
:Neomake vimhelplint
```

## Integration in CI

You can run the plugin automatically as follows, e.g. on Travis CI:

```sh
vim -esN --cmd 'set rtp+=path/to/vim-vimhelplint' -c 'filetype plugin on' \
    -c 'e doc/yourplugin.txt' -c 'verb VimhelpLintEcho' -c q
```
