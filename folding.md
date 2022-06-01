6. Folding/Outline                                           *vimwiki-folding*

Vimwiki allows you to use Vim's folding methods and options so you can fold
your outline to make it less distracting and easier to navigate. You can use
Vimwiki's built-in folding methods or supply custom methods for folding.  You
control how folds behave with by setting the |g:vimwiki_folding| variable to
the desired value in your configuration file: >

  let g:vimwiki_folding = 'value'

Here's an example of how folds work with |g:vimwiki_folding| set to 'list':

= My current task =
* [ ] Do stuff 1
  * [ ] Do substuff 1.1
  * [ ] Do substuff 1.2
    * [ ] Do substuff 1.2.1
    * [ ] Do substuff 1.2.2
  * [ ] Do substuff 1.3
* [ ] Do stuff 2
* [ ] Do stuff 3

Hit |zM| :
= My current task =
* [ ] Do stuff 1 [6] --------------------------------------~
* [ ] Do stuff 2
* [ ] Do stuff 3

Hit |zr| :
= My current task =
* [ ] Do stuff 1
  * [ ] Do substuff 1.1
  * [ ] Do substuff 1.2 [3] -------------------------------~
  * [ ] Do substuff 1.3
* [ ] Do stuff 2
* [ ] Do stuff 3

Hit |zr| one more time :
= My current task =
* [ ] Do stuff 1
  * [ ] Do substuff 1.1
  * [ ] Do substuff 1.2
    * [ ] Do substuff 1.2.1
    * [ ] Do substuff 1.2.2
  * [ ] Do substuff 1.3
* [ ] Do stuff 2
* [ ] Do stuff 3

Note: If you use the default Vimwiki syntax, folding on list items will work
properly only if all of them are indented using the current 'shiftwidth'.
For Markdown and MediaWiki syntax, * or # should be in the first column.

For maximum control over folds, set |g:vimwiki_folding| to 'custom' so you can
allow other plugins or your vim configuration file to control how folding is
performed. For example, let's say you are using markdown syntax and prefer to
fold so that the last blank line before a header is not folded, you can add
this function to your configuration file: >

  function! VimwikiFoldLevelCustom(lnum)
    let pounds = strlen(matchstr(getline(a:lnum), '^#\+'))
    if (pounds)
      return '>' . pounds  " start a fold level
    endif
    if getline(a:lnum) =~? '\v^\s*$'
      if (strlen(matchstr(getline(a:lnum + 1), '^#\+')))
        return '-1' " don't fold last blank line before header
      endif
    endif
    return '=' " return previous fold level
  endfunction

Note that you will also need to add the following vim options to your configuration: >

  augroup VimrcAuGroup
    autocmd!
    autocmd FileType vimwiki setlocal foldmethod=expr |
      \ setlocal foldenable | set foldexpr=VimwikiFoldLevelCustom(v:lnum)
  augroup END

See the |g:vimwiki_folding| documentation for more details.
