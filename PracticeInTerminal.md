# Practice in the Terminal
## The Command Line!
- There are two types of interface : CLI(command line interface) and GUI (graphical user interface)
- A command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.

-The command line typically presents you with a prompt As you type, it will be displayed after the prompt. Most of the time you will be issuing commands.

![Terminal image](/images/Terminal.png)
This is an image of my Terminal:
- As we said, we will enter a command and the terminal will excute it and display the output for us.
- every command has its own Abbreviation such as (ls) which mean Listing Directory and (cd) is refer to Change Directory and so on..

- sometimes we type space and then type dash (-) then some Abbreviation such as (ls -l),command line argument ( -l ) is also referred to as an option. Options are typically used to modify the behaviour of the command. Options are usually listed before other arguments and typically start with a dash ( - ).
- after we type the command we will see the output.. and if there is a problem , it will show us an error and what type is it.
- If no prompt is displayed then the command may still be running.
> When you enter commands, they are actually stored in a history. You can traverse this history using the up and down arrow keys. So don't bother re-typing out commands you have previously entered, you can usually just hit the up arrow a few times. You can also edit these commands using the left and right arrow keys to move the cursor where you want. [Important Terminal commands](https://www.techrepublic.com/article/16-terminal-commands-every-user-should-know/)

## Basic Navigation!
### Some important commands that we have to know :
1. pwd: Print Working Directory - ie. Where are we currently.
2. ls : List the contents of a directory.
3. cd: Change Directories - ie. move to another directory.

### Important Concepts:
- Relative path: A file or directory location relative to where we currently are in the file system.
- Absolute path: A file or directory location in relation to the root of the file system.
### Paths
- ~ (tilde) - This is a shortcut for your home directory. eg, if your home directory is /home/ryan then you could refer to the directory Documents with the path /home/ryan/Documents or ~/Documents
- . (dot) - This is a reference to your current directory. eg in the example above we referred to Documents on line 4 with a relative path. It could also be written as ./Documents (Normally this extra bit is not required but in later sections we will see where it comes in handy).
- .. (dotdot)- This is a reference to the parent directory. You can use this several times in a path to keep going up the hierarchy. eg if you were in the path /home/ryan you could run the command ls ../../ and this would do a listing of the root directory.
- If you run the command cd without any arguments then it will always take you back to your home directory.
> Tab Completion:
> When you start typing a path (anywhere on the command line, you're not just limited to certain commands) you may hit the Tab key on your keyboard at any time which will invoke an auto complete action. If nothing happens then that means there are several possibilities. If you hit Tab again it will show you those possibilities. You may then continue typing and hit Tab again and it will again try to auto complete for you.

## More About Files!
- file : obtain information about what type of file a file or directory is.
- (ls -a) command : List the contents of a directory, including hidden files.
- Spaces in names: There are two ways to write the file name that contain of 2 or more words 
  1. The first approach involves using quotes around the entire item. You may use either single or double quotes, Anything inside quotes is considered a single item.('Holiday Photos')
  2. Another method is to use what is called an escape character, which is a backslash ( \ ) - (Holiday\ Photos)

### Important Concepts:
- Everything is a file under Linux : Even directories.
- Linux is an extensionless system : Files can have any extension they like or none at all.
- Linux is case sensitive : Beware of silly typos.

## Manual Pages!
- man \<command\>
   - Look up the manual page for a particular command.
- man -k \<search term\>
   - Do a keyword search for all manual pages containing the given search term.
- /\<term\>
   - Within a manual page, perform a search for 'term'.
- n
   - After performing a search within a manual page, select the next found item.
- To exit the man pages press 'q' for quit.

#### There are two type of hand :
1. long hand.
2. short hand. 
- As example: To list all directory entries (including hidden files) we can use the option -a (short hand) or --all (long hand). 
    - The long hand is really just a more human readable form. You may use either, they both do the same thing. 
    - One advantage of using long hand is that it can be easier for you to remember what your commands are doing.
    - One advantage of using shorthand is that you can chain multiple together easier.
 
 long hand command line options begin with two dashes ( -- ) and short hand options begin with a single dash ( - ). 

## File Manipulation!

- mkdir [options] \<Directory\>
    - Make Directory - ie. Create a directory.
       - -p which tells mkdir to make parent directories as needed.
       - -v which makes mkdir tell us what it is doing.
> Examples:
> - mkdir linuxtutorialwork
> - mkdir /home/ryan/foo
> - mkdir ./blah
> - mkdir ../dir1
> - mkdir ~/linuxtutorialwork/dir2
- rmdir [options] \<Directory\>
    - Remove Directory - ie. Delete a directory.
- touch [options] \<filename\>
    - Create a blank file.
- cp [options] \<source\> \<destination\>
    - Copy - ie. Copy a file or directory.
    > cp example1 barney
- mv [options] \<source\> \<destination\>
    - Move - ie. Move a file or directory (can also be used to rename).
- rm [options] \<file\>
    - Remove - ie. Delete a file.
    - -r option is used to Removing non empty Directories

### Important Concepts:
- No undo: The Linux command line does not have an undo feature. Perform destructive actions carefully.
- Command line options: Most commands have many useful command line options. Make sure you skim the man page for new commands so you are familiar with what they can do and what is available.

## Cheat Sheet: [Terminal Cheat Sheet ](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)
- cheat sheet help us to find all commands that we need it in terminal.
- There are many cheat sheet for many langauges , such as markdown.
