: ' Run this file as a bash script to view documentation in man page format
<!--
'
pandoc -s -f markdown -t man $0 | man -l - ; exit
: '
-->
'

Basic vim shortcuts for myself rememberance
=

### Cursor movement & Scrolling

- Alt+hjkl - move cursor with exiting in normal mode if was in insert mode  
  Alt generates Esc so any normal mode commands are available in insert mode via Alt  
- w - jump by start of words (punctuation considered words)  
- W - jump by words (spaces separate words)  
- e - jump to end of words (punctuation considered words)  
- E - jump to end of words (no punctuation)  
- b - jump backward by words (punctuation considered words)  
- B - jump backward by words (no punctuation)  
- 0 - (zero) start of line  
- ^ - first non-blank character of line  
- $ - end of line  
- xG - Go To command (prefix with number - 5G goes to line 5)  
- gg - go to BOF  
- G - go to EOF  
- Ctrl+d, Ctrl+u - scroll half a page up, down  
- Ctrl+f, Ctrl+b - scroll page up, down  
- zz - set current line at center of window  
- zb - set current line at bottom of window  
- zt - set current line at top of window  
- n - next matching search pattern  
- N - previous matching search pattern  
- «*» - next word under cursor  
- «#» - previous word under cursor  
- g* - next matching search pattern under cursor  
- g# - previous matching search pattern under cursor  
- % - jump to matching bracket { } [ ] ( )  
- f{char} - Jump to next occurrence of {char} in current line  
- F{char} - Jump to previous occurrence of {char} in current line   
- ; - Repeat last f/F/t/T movement  

### Movement: Code

- % - Jump between opening/closing braces, brackets, parentheses, etc.  
- [[ - Jump to previous function  
- ]] - Jump to next function  
- [{ - Jump to beginning of current block  
- ]} - Jump to end of current block  

### Code indenting

- Ctrl+t Indent current line (Insert mode)  
- Ctrl+d Unindent current line (Insert mode)  
- [n]> - shift right [n] times selected text  
- [n]< - shift left [n] times selected text  
- [n]>> - shift right one time [n] lines while in normal mode  
- [n]<< - shift left one time [n] lines while in normal mode  
- ">aB" - Indent current block (defined by curly braces)  
- ">i{" - Indent inside current set of curly braces  

### Deleting text

- dw - Delete a word  
- dd - Delete line  
- S - Change line. Empty line and switch to Insert mode  
- C - Change rest of the line. Remove all after cursor and switch to Insert mode  
- di( - Delete inside parentheses. (You can be anywhere inside them.)  
- dit - Delete inside tag. (Meaning, delete what's between the opening and closing tags.)  
- dt{char} - Delete to {char} in current line. Also works with f  

### Deleting text (Insert mode)

- Ctrl+w - Delete a word before cursor  
- Alt+c,w - Delete a word after cursor  
- Alt+c,e - Delete a word after cursor. Space is not a word  
- Ctrl+d - Delete a word after cursor (Macros have to be defined in .vimrc file: inoremap <C-d> <space><esc>ce)  
- Ctrl+u - delete to beginning of indent  

### Select text (visual mode)

- v - start visual mode, mark lines, then do command (such as y-yank)  
- V - start Linewise visual mode  
- o - move to other end of marked area  
- Ctrl+v - start visual block mode  
- O - move to Other corner of block  
- aw - mark a word  
- ab - a () block (with braces)  
- aB - a {} block (with brackets)  
- ib - inner () block  
- iB - inner {} block  
- gv - reselect block  
After selecting the text, try d to delete, or y to copy, or :s/match/replace/, or :center, or !sort, or >> to indent or << to unindent or ...  
- . - to repear last command  

### Editing

- ~ - switch char case  
- J - Join line (pull the next line up after the end of the current line)

### How to Exit

- ZZ - Write current file, if modified, and exit  
- ZQ - Quit current file and exit (same as ":q!")  

### Undo/Redo

- u - Undo  
- Ctrl+r - Redo  

### Marks

- m{a-zA-Z} - Set mark {a-zA-Z} at cursor position (does not move the cursor, this is not a motion command)  
- `{a-z} - To the mark {a-z}  
- '{a-z} - To the first non-blank character on the line with mark {a-z}  
- `` `" - go to position before jump, at last edit  

### Buffers

- :ls — list opened files (buffers)  
- :bd — close opened file (buffer)  
- :b {N} — select buffer {N} to show in current window  
- :bn — select next buffer  
- :bp — select previous buffer  

### Windows

- :split - Split window (one window on top of the other)  
- :vsplit - Split window (one window next to the other)  
- :split [file] - Split window and open [file] in the new window  
- :close Close current window  
- :only - Close every window except for the current one  
- Ctrl+w,h - Move focus to the window to the left  
- Ctrl+w,j - Move focus to the window underneath  
- Ctrl+w,k - Move focus to the window above  
- Ctrl+w,l - Move focus to the window to the right  
- Ctrl+w,w - Move focus to the window below/right of the current one  
- Ctrl+w,W - Move focus to the window above/left of the current one  

### Miscellaneous

- ga - show ASCII value of character under cursor  
- g+Ctrl+G - show cursor column, line, and character position  


### Find and Replace

- :%s/search/replace/g - Replace all instances of 'search' with 'replace' throughout the whole file  
- :%s/search/replace/gc - Replace all instances of 'search' with 'replace' throughout the whole file with confirmation  
- :g/foo/ s/bar/BAR/g - On lines that match the regex /foo/, replace 'bar' with 'BAR'  


