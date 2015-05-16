# Vimprove
A series of daily tasks/info to learn vim from beginner to expert one day at a time.
Once installed it gives you new tips in your console every day.
It aims to walk users through new features over time, giving the user time to
learn concepts as they slowly expand their understanding of vim. For this
reason some concepts are explained using different terminology (files instead
of buffers) to aid understanding.

## Installation
- Clone the repo:
```bash
    git clone https://www.github.com/ChrisPenner/vimprove
```

- Run the installation script, then delete the folder.
(The program and tips will be stored in your `~/.vimprove` folder)

```bash
    ./vimprove/install
```

- Lastly add this call to your .bashrc (or your profile file).
    This will cause vimprove to print out your tips every time you open a new
    console.

```bash
    alias vimprove="~/.vimprove/vimprove"
    vimprove
```

- You can now safely delete the github repo you cloned.

## Usage
Vimprove will do its very best to be self-sufficient. Each day that it's run it
will update the vim tips shown by adding a new one and deleting the oldest (if
you've hit the max number of tips, see below to change this). That being said,
if you want to manage it manually there's some commands built in.

The whole thing is built in bash and plain-text, so if you want to add your own
tips, just follow the same format and it'll probably just work.

- Get help:

```bash
    vimprove help
```

- Change the number of tips shown at a time:

```bash
    vimprove numtips <number>
```

- Cycle to the next tip

```bash
    vimprove next
```

- Remove a tip from your displayed tips:

```bash
    vimprove clear <number>
```

- Add a tip to your displayed tips:

```bash
    vimprove add <number>
```

- Hide the header message

```bash
    vimprove hide
```

- Show the header message

```bash
    vimprove show
```

## The Tips
Feel free to read through them now, but you'll learn them much better if you learn
them a few at a time!

1. Run the `vimtutor` command (on the terminal) and complete Section 1
2. Remember, use `hjkl` to move around.
3. `i` enters insert mode, where vim works like most editors.
4. In `normal` mode every key is its own command.
    Press `<escape>` to return to normal mode.
    Assume each command is for normal mode unless I say otherwise.
5. In normal mode `:` enters command mode, try `:help<cr>`
    Curious what a key does? `:help <keysequence><cr>` to learn!
    `<cr>` means to press the 'enter'/'return' key.
    for now just try `:help<cr>`
    I'll refer to command mode commands with the {C} label when they come up.
6. {C} `:w` saves the file. `:q` quits, `:wq` saves and quits!
7. Work through Section 2 of `vimtutor`.
    Going through vimtutor helps you to remember commands you've forgotten.
8. {C} :e <file>` opens a file for editing.
9. If you want to show more tips at a time, run `vimprove numtips 'n'`,
    Where 'n' is the max number of tips to show at a time.
10. Hitting escape is annoying. It's far away.
     Try rebinding your caps-lock key to escape instead! (try 'Seil'!)
11. If you've got a tip mastered, run `vimprove clear 'n'` to clear tip 'n'.
12. `w` moves the cursor forward by one 'word'
     Try `:help iskeyword` to learn about what makes a 'word'.
13. `b` moves the cursor backward by one 'word'
14. `W` moves the cursor forward by one 'WORD'
     A 'WORD' is a contiguous group of non-whitespace characters,
     basically this jumps to past the next space.
     `B` goes back one 'WORD' as the clever among you may have suspected.
15. `x` deletes the char under the cursor.
     `X` deletes the char before the cursor.
16. Time to make our .vimrc, this is a configuration file that defines a set
     of commands we want Vim to run when it starts up. run `:e ~/.vimrc` and
     add a command to set the colorscheme when Vim starts up.
     E.g. colorscheme desert
     Search online if you get stuck!
17. Now you've got a .vimrc! You can store mappings, settings, functions and
     all sorts of cool things in there. Try to keep it organized, we'll learn
     about mappings in a bit!
18. To move to the next tip, run `vimprove next`.
     Make sure you're trying out each tip as you read it!
19. Try finishing off vimtutor today!
20. Use `I` to start inserting text at the beginning of the current line.
     Use `A` to insert text at the end of the current line.
21. Try `u` to undo your mistakes! Hit it multiple times to undo more.
     `<C-r>` to redo changes, (`<C-r>` means hold 'control' key and press 'r')
22. `f<char>` will move forward to the next <char> in the current line.
     `F<char>` does the same, but moves backwards in the current line.
23. `0` jumps to the beginning of the current line.
     `$` jumps to the end of the line.
24. `v` starts a visual selection.
     Use any motions you know to extend the selection.
25. {v} In visual mode, use `d` to delete the selection.
26. `yw` copies (yanks) one word into the clip-board
     `p` pastes whatever is in the clipboard.
27. {v} Press `y` to yank the currently selected text to the clipboard.
28. {v} Use `c` to 'change' your selection,
     That is, to delete it and enter insert mode.
29. `dd` deletes the current line.
30. `C` 'changes' from the cursor to the end of the line.
31. Things like `w`, `f<char>` and `$` are called 'motions'
     Things like `d`, `c`, and `y` are called 'operators'
     Operators use motions to define an area to perform their function on.
     Read up: (:h operator)
32. In the command `d$`:
     the `d` means 'delete' and the `$` means 'move to end of line'
     So `d$` means 'delete to the end of the line'
     You'll find most operators and motions can be combined in this way.
33. Oftentimes repeating an operator means "for the whole line"
     E.g. `yy`: yank one line, `dd`: delete one line, `cc`: change one line.
34. Enter search mode with `/`, type what you're looking for then press enter.
     `?` Searches backwards.
35. `n` finds the next search result, `N` finds the previous one.
     The behaviour is reversed when the search was started with `?`.
36. `V` starts a 'line-wise' visual selection.
37. `.` is a special command.
     It repeats the last change you made in a new spot.
     E.g. Use `cw` to change a word to something else, then move to a new word
     and press `.`, Vim will change that word to the new word as well!
     This is very helpful for repetitive tasks! See (:h .)
38. `a` starts insert mode at the position AFTER the cursor.
39. `r<char>` replaces the character under the cursor with <char>.
40. Try out some more operator + motion combos!
     Try `d/` then enter a search term to delete up to the first occurance!
     `yf.` will 'yank' up to and including the next period.
41. Most commands can take a numeric count. Type the number, then the command.
     E.g. `5dd` will delete 5 lines, `3n` searches forwards 3 occurences.
     Even `i` can take a count. Try `10i`, type something, then <esc>.
42. `o` starts insert on a new line BELOW the current one.
     `O` starts insert on a new line ABOVE the current one.
43. `ZZ` is a quick way to save and quit all files.
44. Time for something new, Mappings. Every key you press is mapped to
     something, right now the keys are mapped to their literal value, but we can
     change that. Any key-sequence can be 'mapped' any other key sequence.
     Try entering `:imap jk <esc>` then press return.
     Now, pressing `jk` in insert mode will act as though you pressed escape!
45. Note that you can specify a specific mode for a mapping to take place.
     imap is for insert, nmap is for normal, vmap is for visual and cmap is for
     the command line. For reasons I'll explain later, it's good practice to
     use the non-recursive versions of these:
     inoremap, nnoremap, vnoremap, cnoremap.
46. Add a few mappings to your `~/.vimrc` search online for ideas of some
     things to add.
47. When adding mappings it's a good idea to define a 'leader' key.
     This is a key that acts as a prefix for YOUR commands.
     Common choices for this key are `\`, `<space>` and `,`
     Since they're easy to use and their default functionality isn't vital.
     Set a leader in your `~/.vimrc` like this: `let mapleader='<key>'`
     where <key> is your leader of choice.
48. Time to use that leader for a mapping!
     Define a new mapping to save the current file.
     Try something similar to `nnoremap <leader>s :w<cr>`
49. Remember that mappings are very flexible and that even a single keystroke
     can be mapped to any keystrokes, functions, or plugins you like!
     Try to know what a key does before you map over it though, it might be
     useful!
50. Though most useful commands are mapped to single keys, some are mapped to
     combinations or use modifiers.
     <C-f> (That is, CTRL+f) will scroll forward one screen.
     <C-b> will scroll back one screen.
51. Any time you use something like a motion or search to jump around in vim,
     it keeps track of where you came from in something called the 'jumplist'.
     Use `<C-o>` and `<C-i>` to go backwards and forwards through the jump list.
     Try it now!
