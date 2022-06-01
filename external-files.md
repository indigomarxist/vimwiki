External files~

The "file:" and "local:" schemes allow you to directly link to arbitrary
resources using absolute or relative paths: >
  [[file:/home/somebody/a/b/c/music.mp3]]
  [[file:C:/Users/somebody/d/e/f/music.mp3]]
  [[file:~/a/b/c/music.mp3]]
  [[file:../assets/data.csv|Important Data]]
  [[local:C:/Users/somebody/d/e/f/music.mp3]]
  [[file:/home/user/documents/|Link to a directory]]
  
  [file:~/Documents/archive/img/akira-reversed.png](file:~/Documents/archive/img/akira-reversed.png)
  
These links are opened with the system command, i.e. !xdg-open (Linux), !open
(Mac), or !start (Windows).  To customize this behavior, see
|VimwikiLinkHandler|.

In Vim, "file:" and "local:" behave the same, i.e. you can use them with both
relative and absolute links. When converted to HTML, however, "file:" links
will become absolute links, while "local:" links become relative to the HTML
output directory. The latter can be useful if you copy your HTML files to
another computer.
To customize the HTML conversion of links, see |VimwikiLinkConverter|.
