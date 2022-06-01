### vimwiki-commands
    *:h vimwiki for more*
    
[syntax](syntax)
[external files](external-files)
[mardown links](mardown-links)
[headers](headers)
[folding](folding)
[tables](tables)
[markdown export](markdown-export)
[toc](toc) 

    **:help vimwiki-commands** -- List all commands.
    **:help vimwiki** -- General vimwiki help docs.
    
    **:VimwikiTOC** -- Create or update the Table of Contents for the current wiki file.
    See *|vimwiki-toc|.*
    
    **:VimwikiTable** -- Create a table with 5 cols and 2 rows.

    **:VimwikiTable cols rows** -- Create a table with the given cols and rows

    **:VimwikiTable cols** -- Create a table with the given cols and 2 rows
    
    **:help group-name** -- highlighting
    
    :**put =expand('%:p')** -- Insert file path
    **:put =expand('#:p')** -- Insert file path
