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

### [Tip 5]()
### [Tip 5]()
### [Tip 5]()
