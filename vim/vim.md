# Vim



## Wrap text 

https://tpope.io/vim/surround.git ~/.vim/bundle/surround 

Adding

```
yss"
```

Adding only around one word

```
ysiw"
```


Delete surrounding tags 

```
dst
```
Delete surrounding tags 

```
ds'
```

Change surrounding tags 

```
cst<new tag>
```

# Screen 

## Rename screen window

ctl+a shift+a






# Change Case

 ~    : Changes the case of current character

 guu  : Change current line from upper to lower.

 gUU  : Change current LINE from lower to upper.

 guw  : Change to end of current WORD from upper to lower.

 guaw : Change all of current WORD to lower.

 gUw  : Change to end of current WORD from lower to upper.

 gUaw : Change all of current WORD to upper.

 g~~  : Invert case to entire line

 guG : Change to lowercase until the end of document.
 
 # Ctags
 
 Install 
 ```
 $ sudo apt-get install ctags
 ```

Create tag files 
```
$ ctags -R.
```

Usage 

- Type <C-]> to jump to a symbol. Keep typing to build a stack of symbols.
- Type <C-t> to jump back. Pop back to where you last were. Works until the stack of symbols is exhausted.
 
# Rotate windows in vim 

```Ctrl-w H``` or type ```:wincmd H``` to go from horizontal to vertical layout.

```Ctrl-w J``` or type ```:wincmd J``` to go from vertical to horizontal layout.

```Ctrl-w r``` or type ```:wincmd r``` to swap the two buffers but keep the window layout the same.

```Ctrl-w w``` or type ```:wincmd w``` to move the cursor between the two windows/buffers.

# Kill a screen window 

select stalled window ( C-a :select <stalled window number> )
send kill command ( C-a :kill )
 
# Reindent the entier file 
gg=G

# yank lines without moving the cursor using relative numbers 

: +2, +3y # this will copy the line below 
: -3, -2y # this will copy the line above 

# search and replace a char by new line 
:%s/Search_term/\r/gc

# Scroll in screen window 
Ctr+a UP_ARROW | DOWN_ARROW



https://www.youtube.com/watch?v=wlR5gYd6um0&t=1420s


# Folding

-  

# NeoVim

```
:scr[iptnames]
```
- List all sourced script names, in the order they were first sourced.  The number is used for the script ID


