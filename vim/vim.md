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
 
