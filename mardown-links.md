Markdown Links~

These links are only available for Markdown syntax.  See
http://daringfireball.net/projects/markdown/syntax#link.

Inline link: >
  [Looks like this](URL)

Image link: >
  ![Looks like this](URL)

Reference-style links: >
  a) [Link Name][Id]
  b) [Id][], using the "implicit link name" shortcut

Reference style links must always include two consecutive pairs of
[-brackets, and field entries can not use "[" or "]".


NOTE: (in Vimwiki's current implementation) Reference-style links are a hybrid
of Vimwiki's default "Wikilink" and the tradition reference-style link.

If the Id is defined elsewhere in the source, as per the Markdown standard: >
  [Id]: URL

then the URL is opened with the system default handler.  Otherwise, Vimwiki
treats the reference-style link as a Wikilink, interpreting the Id field as a
wiki page name.

Highlighting of existing links when |vimwiki-option-maxhi| is activated
identifies links whose Id field is not defined, either as a reference-link or
as a wiki page.

To scan the page for new or changed definitions for reference-links, simply
re-open the page ":e<CR>".
