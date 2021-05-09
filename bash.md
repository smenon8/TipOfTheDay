# Bash Tip of the Day

### [Tip 1](https://www.linkedin.com/posts/smenon8_tipoftheday-bashshell-day1-activity-6775533367044796416-hmx_)  
Quickly execute the last command you ran:   
Type `!!` on your terminal and hit enter.

### [Tip 2](https://www.linkedin.com/posts/smenon8_tipoftheday-day2-bashshell-activity-6775856610268061696-r_QP)
Re-execute a really long command that you ran long ago:   
Type `!?<part of the command>` and hit enter.

### [Tip 3](https://www.linkedin.com/posts/smenon8_day3-tipoftheday-activity-6776234106528387073-ndYh)
When you only remember part of the command you ran long ago:
Run `Ctrl + R` and type the part you remember.   
It does a reverse search through your bash history.
You can keep hitting `Ctrl+R` to cycle through.    
Use Ctrl on both Mac and Windows.

### [Tip 4](https://www.linkedin.com/posts/smenon8_n-day4-tipoftheday-activity-6776577699227017216-mGOK)
Using history effectively:

To run command #n from history:   
Run `!n` where n is the nth command in `history`.   
Ex. `!20` will run 20th command from history


Bonus tip: also works with negative numbers:  
!-1 executes the last command and !-2 the one before last command and so on.


### [Tip 5](https://www.linkedin.com/posts/smenon8_tmux-shortcuts-cheatsheet-activity-6777275974653497344-rcta)
Switching terminal windows.

Use `tmux`.
Once in a tmux window, use ctrl + “ to split window horizontally and use ctrl + % for vertically splitting.   
[`tmux` cheatsheet](http://ow.ly/fBEi50DYpt0)


### [Tip 6](https://www.linkedin.com/posts/smenon8_day6-tipoftheday-part1-activity-6777634916189528065-ZFZt)
Customize your auto-completions part 1 of 2.
Ex. 
```
$ command [arg|some|other|param]
```

To see completions, <arg, some, other, param> after you type “command” and hit <tab> twice, run   
  
```
$ complete -W “arg some other param” command
```
  
Then,
```
$ command <tab><tab>
arg some other param
```
Displays all the available params in stdout. 
Add it to your .bashrc if you use it very often.

### [Tip 7](https://www.linkedin.com/posts/smenon8_tipoftheday-day7-activity-6777997326297509888-4Izy)
Customize your auto-completions part 2.
Cases where your command/script takes in files with certain extensions, you can use `complete` to only shows files with that extension.

```
$ complete -f -X ‘!*.csv’ command
# to only show csv files from the current directory
```

P.S. This is auto-complete in its truest form.  
So, `command prefix<tab><tab>` will only show `prefix*.csv` files from current directory.


### [Tip 8](https://www.linkedin.com/posts/smenon8_tipoftheday-day8-activity-6778359811487727617--me5)
reuse the last argument for a different command?

For ex.
```
$ old_command /really/really/really/really/long/path
# If you want to reuse the argument for a new command, just run
$ new_command $_
```
I find it useful for the subsequent ls then cd situations. 

### [Tip 9](https://www.linkedin.com/posts/smenon8_tipoftheday-day9-activity-6778722123604226048-jIpj)
Configure your key-bindings to filter commands from history based on prefix:
Say you have the below contents in your bash history
command arg1
command arg2
random cmd

Run,
```
bind '"\e[A": history-search-backward' # bind up arrow key
bind '"\e[A": history-search-forward'  # bind down arrow key
```
After this,
```
command <up or down arrow key>
# Will cycle through only arg2 and arg1
```

### [Tip 10](https://www.linkedin.com/posts/smenon8_tipoftheday-day10-activity-6779084357127806976-W7i6)
Display status code of your last command in your prompt:

`$?` stores the return code of last command, so you can add this to your `.bashrc` or `.bash_profile`
```
PS1 += “ [ \$? ]”
```
For full colored customization of your prompt with exit status: https://lnkd.in/g8KHyEy


### [Tip 11](https://www.linkedin.com/posts/smenon8_tipoftheday-day11-activity-6779812691465916416-nkDU)
Tired of waiting for your long running command to complete but it’s important enough to monitor the output?

`watch` to your rescue.

```
$ watch <command> # Will monitor the output of the command every 2 seconds.
$ watch -n <seconds> <command> # monitor command every n seconds
$ watch -d <command> # monitor every 2 seconds and highlight differences with last output
```

### [Tip 12](https://www.linkedin.com/posts/smenon8_tipoftheday-day12-activity-6780175061702852608-oXu2)
Typing a really long complex command on the shell can often get messy, even with line separators.

Type `Ctrl+X` then `Ctrl+E` to open an editor (vi) and enter your command there.

### [Tip 13](https://www.linkedin.com/posts/smenon8_tipoftheday-day13-activity-6780537465724919808-iQeu)
Cutting and pasting on the shell is often messy and involves multiple keystrokes and/or mouse.

You can now cut the last token from the shell using `Ctrl + W`, and then use `Ctrl + Y` to paste that token.   
Note: this only works for tokens and a token is the last word typed after the space delimiter.

### [Tip 14](https://www.linkedin.com/posts/smenon8_readline-killing-commands-bash-reference-activity-6780899851560452096-llgE)
Killing(cut) and yanking(paste) text - advanced

This is a continuation of cut and paste shortcut tip

`Ctrl + K` : cut everything from the current cursor position till the end of line
`Ctrl + Y`: to paste the contents.

There are many more kill & yank shortcuts to master here: https://lnkd.in/gMrDVyX   
Consider using a clipboard manager if you want to preserve and manage the contents of your clipboard.
On Linux (or any other GNOME based distributions), try GPaste.

