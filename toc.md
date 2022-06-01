Table of Contents                    *vimwiki-toc* *vimwiki-table-of-contents*

You can create a "table of contents" at the top of your wiki file.
The commando |:VimwikiTOC| creates the magic header >
  = Contents =
in the current file and below it a list of all the headers in this file as
links, so you can directly jump to specific parts of the file.

For the indentation of the list, the value of |vimwiki-option-list_margin| is
used.

If you don't want the TOC to sit in the very first line, e.g. because you have
a modeline there, put the magic header in the second or third line and run
:VimwikiTOC to update the TOC.

If English is not your preferred language, set the option
|g:vimwiki_toc_header| to your favorite translation.

If you want to keep the TOC up to date automatically, use the option
|vimwiki-option-auto_toc|.
