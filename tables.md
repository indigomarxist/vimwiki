9. Tables                                                     *vimwiki-tables*
    [summary](#commands-summary)
    [commands](#table commands)
Use the  :VimwikiTable command to create a default table with 5 columns and 2
rows: >

 |   |   |   |   |   |
 |---|---|---|---|---|
 |   |   |   |   |   |
<

Tables are auto-formattable. Let's add some text into first cell: >

 | First Name  |   |   |   |   |
 |---|---|---|---|---|
 |   |   |   |   |   |
<

Whenever you press <TAB>, <CR> or leave Insert mode, the table is formatted: >

 | First Name |   |   |   |   |
 |------------|---|---|---|---|
 |            |   |   |   |   |
<

You can easily create nice-looking text tables, just press <TAB> and enter new
values: >

 | First Name | Last Name  | Age | City     | e-mail               |
 |------------|------------|-----|----------|----------------------|
 | Vladislav  | Pokrishkin | 31  | Moscow   | vlad_pok@smail.com   |
 | James      | Esfandiary | 27  | Istanbul | esfandiary@tmail.com |
<

To indent table indent the first row. Then format it with 'gqq'.

You can specify the type of horizontal alignment for columns in the separator
using the ':' character. The default is left-align.  >

 | Date       |  Item  |   Price |
 |------------|:------:|--------:|
 | yest       | Coffee |  $15.00 |
 | 2017-02-13 |  Tea   |   $2.10 |
 | 2017-03-14 |  Cake  | $143.12 |
<

#ff00ff
### commands-summary
    **:VimwikiTable** -- Create a table with 5 cols and 2 rows.

    **:VimwikiTable cols rows** -- Create a table with the given cols and rows

    **:VimwikiTable cols** -- Create a table with the given cols and 2 rows
    
### table commands
*:VimwikiTable*
    Create a table with 5 cols and 2 rows.

    :VimwikiTable cols rows
    Create a table with the given cols and rows

    :VimwikiTable cols
    Create a table with the given cols and 2 rows


*:VimwikiTableMoveColumnLeft* , *:VimwikiTableMoveColumnRight*
    Move current column to the left or to the right:
    Example: >

    | head1  | head2  | head3  | head4  | head5  |
    |--------|--------|--------|--------|--------|
    | value1 | value2 | value3 | value4 | value5 |


    Cursor is on 'head1'.
    :VimwikiTableMoveColumnRight

    | head2  | head1  | head3  | head4  | head5  |
    |--------|--------|--------|--------|--------|
    | value2 | value1 | value3 | value4 | value5 |

    Cursor is on 'head3'.
    :VimwikiTableMoveColumnLeft

    | head2  | head3  | head1  | head4  | head5  |
    |--------|--------|--------|--------|--------|
    | value2 | value3 | value1 | value4 | value5 |
