# asyncomplete-user.vim

User completion source for [asyncomplete.vim](https://github.com/prabirshrestha/asyncomplete.vim)

(`:h compl-function`)

## Install

```vim
Plug 'prabirshrestha/asyncomplete.vim'
Plug 'jsit/asyncomplete-user.vim'
```

## Register asyncomplete-user.vim

```vim
call asyncomplete#register_source(asyncomplete#sources#user#get_source_options({
\ 'name': 'user',
\ 'whitelist': ['*'],
\ 'blacklist': ['c', 'cpp', 'html'],
\ 'completor': function('asyncomplete#sources#user#completor')
\  }))
```

## Note

If `completefunc` change cursor position, `asyncomplete-user.vim` does not work correctly.

For example, c, cpp, HTML are blacklisted above because Vim's default `completefunc` repositions the cursor leading to quirky behaviour. You can reenable if you are using a more appropriate `completefunc`.

### Not work correctly

- `rubycomplete#Complete`
