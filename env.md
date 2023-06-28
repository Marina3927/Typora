**0621**

```zsh
git config merge.tool vimdiff
git config merge.conflictstyle diff3
git config mergetool.prompt false

# when merge conflicts, run
git mergetool

:diffg RE  " get from REMOTE
:diffg BA  " get from BASE
:diffg LO  " get from LOCAL
:wqa
git commit

#
git clean 
```



**0620**

```zsh
You can use the >> operator. This will append data from a command to the end of a text file.
To test this try running:

echo "Hi this is a test" >> textfile.txt

Do this a couple of times and then run:

cat textfile.txt
You'll see your text has been appended several times to the textfile.txt file.
```



**0616**

回溯算法back tracking 八皇后算法 dfs

**0615**

```zsh
git pull --rebase
# discard local changes
git reset --hard HEAD
```

**0614**

Go to Symbol `workbench.action.gotoSymbol` Ctrl+Shift+O (Cmd+Shift+O on a Mac).

You can reassign it to Ctrl+R.

You can also group them by typing colon `@:`.

**0607**

A benchmark app is used for [testing computer performance](https://www.softwaretestinghelp.com/computer-stress-test-software/). 

**0529**

```zsh
// Disable gatekeeper
sudo spctl --master-disable
unrar x <filename>
```

**0526**

press f12 to open console in chrome

**0525**

- cmd+m: minimize window

- cmd+tab+arrow+release cmd: Minimized windows back

- **Command + Option and click anywhere on the desktop**: minimize all open windows & access the desktop.
- **Command + Option + H + M**: minimize all apps on Mac and get to the desktop.
- **Command + Option + M**: minimize all windows on the current application.
- **Command + Option + H**: minimize all windows except for the active ones on the top.

**0524**

Sublime-find-ctags

```zsh
# Delete remote directory
git rm -r path/to/directory

#you no longer have a local copy of that branch, but it exists in origin.
git branch -d old_branch   

#If you want to delete the remote branch as well, use
git push --delete origin old_branch
```



**0523**

```zsh
export PATH=$PATH:<path>
source ~/.zshrc
sudo npm --force i -g elm elm-format 
elm-live Main.elm
elm install evancz/elm-playground
killall elm-live
lsof 127.0.0.1
less ../index.html

wget -r -l1 -H -nd -A mp3 -e robots=off http://example/url
pip3 install matplotlib
ls -l
chmod u=rw,og=r new_file.txt
# who: u g o a; which: r w x; what - + =
```

- Ctrl-a:  move cursor to the beginning of the line

- Ctrl-e:  move cursor to the end of the line

- Meta-b:  (or Alt-b), move backward one word

- Meta-f:  (or Alt-f), move forward one word

- Ctrl-u:  Cut from cursor to beginning of line

- Ctrl-k:  Cut from cursor to end of line

- Ctrl-w:  Cut previous word

- Ctrl-y:  Paste what you just cut with Ctrl-u, Ctrl-k, or
           Ctrl-w
       
- Ctrl-_:  Undo last cut (may not work in all terminals)

     

```zsh
git checkou -b dev
git push
|
git push --set-upstream origin dev

git pull
git checkout dev
git merge master
# merge master to dev
elm-live
```



*I accidentally delete all the former contents in env.md. Sorry for the mistake. Apology to you.*

