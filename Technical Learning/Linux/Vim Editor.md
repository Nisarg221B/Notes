
#vim
#vim-editor
(vim editor)

---

### Insert mode 
( #insert-mode-vim)
**To get into insert mode:**

1. Press i (text will be inserted to the right of the current position of the cursor)
2. press I (insert from the beginning of the line)
3. press a (To append text just after the current position)
4. press A (to append text at the end of the currentl line)
5. press O (To insert text in the line above the cursor)
6. press o (To insert in the line below the cursor)

![Different ways of getting into Insert Mode, and how that effects the place where text is inserted.](https://www.learnlinux.org.za/courses/build/images/diagram06.png)

to get out of insert mode press **esc key** 

### **visual mode** ( #movement-vim)

- h,j,k,l for movement in visual mode , you can also use arrows
- shift + >/<       to move the line forward and backward for spacing and alignment.

##### Delete commands ( #delete-operator-vim)
- x delete a charater 
- shortcut to delete and copy a line is 'dd' , you can use 'p' to paste the line afterwards.
- dw to delete a word
- d$ to delete to the end of the line.

Many commands that change text are made from an operator and a motion.

  The format for a delete command with the  d  delete operator is as follows:
        d   motion
   Where:

    d      - is the delete operator.
    motion - is what the operator will operate on (listed below).

  A short list of motions:

    w - until the start of the next word, EXCLUDING its first character.
    e - to the end of the current word, INCLUDING the last character.
    $ - to the end of the line, INCLUDING the last character.

#### Using count for a motion 
( #count-motion-vim)
   ** Typing a number before a motion repeats it that many times. **

  1. Move the cursor to the start of the line below marked --->.
  2. Type  2w  to move the cursor two words forward.
  3. Type  3e  to move the cursor to the end of the third word forward.
  4. Type  0  (zero) to move to the start of the line.
  5. Type $  to move to the end of line

use using the combination from above to headings
-> d2w will be used to delete 2 words 
-> d4w will be used to delete 4 words

##### Undo redo
- u to undo the last change , 2u to undo last two changes
- U  to fix a whole line
- ctrl-r to redo the change

#### Change operator
#change-operator-vim

- Type  rx  to replace the character at the cursor with  x
- Type a capital  R  to replace more than one character (Replace mode is like Insert mode, but every typed character deletes an existing character.)
- ce  deletes the word and places you in Insert mode.
- cc  does the same for the whole line

The change operator works in the same way as delete.  The format is:
         ``c    [number]   motion
         The motions are the same, such as   w (word) and  $ (end of line).
         c$ -> delete till end of line from current position and places you in insert mode
         c4w -> deletes four words and puts you in insert mode.
         
- if you wish to join the line below your current line to the end of the current line use "J" (capital)
- **To tell vim that you wish to save and exit, press "ZZ" (two capital "Z"'s in quick succession).**

#### COPY AND PASTE TEXT
          ** Use the  y  operator to copy text and  p  to paste it **
Start Visual mode with  v  and move the cursor to just before "first".
Type  y  to yank (copy) the highlighted text. and type p to put it wherever you want to.

NOTE: You can also use  y  as an operator:  yw  yanks one word,
           yy  yanks the whole line, then  p  puts that line.


### Movement in vim

For the movement 
![Movement keys in vi](https://www.learnlinux.org.za/courses/build/images/diagram03.png)

Type CTRL-g to show your location in the file and the file status

Press  G  to move you to the bottom of the file.
Type  gg  to move you to the start of the file.

Type the number of the line you were on and then  G .  This will
return you to the line you were on when you first pressed CTRL-G.

#### searching for a word in vim
     ** Type  /  followed by a phrase to search for the phrase. **
     ** press n & N to move to next and previously matched phrase. **

### ex mode
( #ex-mode)
you can enter ex mode  by hitting the ":" key when in visual mode.

: help -> to access the vim's built in help system
: w      -> save
: q       -> quit
: wq    -> save and quit
: q!      -> trash all changes and quit
: x filename -> to save the file not having a name

press esc key to exit the ex mode to visual mode.

for practice use ( "vimtutor" )
