# The command line

## The prompt

The prompt is the place in the terminal where you type commands. By default, it usually shows your computer’s name and your username:

```sh
Alexs-MacBook-Pro:~ alexrandall$ pwd
```

When commands are entered successfully, you don’t always receive feedback that something happened. The usual indication that everything is OK is the appearance of the prompt.

### NOTE

The prompt often starts with a `$`. You installed the [starship prompt](https://starship.rs/) as part of the computer setup instructions. That changed the way your prompt looks and the information it displays. With starship installed, your prompt will start with this character: `❯` instead of `$`.

## Commands

The structure of commands follows a consistent pattern.

Options and arguments are not always required, but different commands have different usages.

```sh
$ command [-options] [arguments]
```

Note: The dollar sign symbol is there to indicate the start of the command line prompt. Don't type that in!

## Arguments

Arguments are information included with a command to modify its behavior.

One or more arguments may usually be included, separated by whitespace.

```sh
$ cal Nov 2018
$ ls ~/Documents/
```

# ⚠️ Remember: don't type in the `$`! That's just there to indicate the start of your command line prompt.

## Options

```sh
# doesn't work because the command requires two arguments
$ cal may

# passing the option -m lets you use a single argument for the month
$ cal -m may


## More arguments and options
$ ls
$ ls ~/Documents/
$ ls -l ~/Documents/
$ ls -lt ~/Documents/
```

## `man` Pages

How do you know what a command does, or what arguments and options a command can accept? The `man` (short for "manual") command accepts the name of other commands as arguments.

```sh
$ man cal
```

## Exiting `man`

man pages use another utility called less to display information. Check out the man pages on it!

To get back to the prompt from less, press "q".

## How to get back to the prompt

# If the command line hangs or you want to stop a process that is ongoing, use the keystroke Ctrl-C. Sometimes you’ll see it written as ^C.

`man` pages use another utility called `less` to display information. Check out the man pages on it!

To get back to the prompt from `less`, press "q".

## How to get back to the prompt

If the command line hangs or you want to stop a process that is ongoing, use the keystroke Ctrl-C. Sometimes you’ll see it written as `^C`.

Try this out by using the following command:

```sh
$ cat
```

Hint: It’s waiting for your input…

## Repeating and editing commands

Up-arrow cycles through commands you’ve typed previously in the same session.

Left-arrow and Right-arrow let you move around the line and edit what you’ve typed.

The command isn’t submitted until you hit Enter/Return.

## `sudo`

### Use with caution!

This command, short for "super user do", appended before you enter any other command, gives you root privileges.

That is, you can execute any command, including modifying sensitive system files.

```sh
$ sudo nano /etc/hosts
```

## Directories

A directory is what you know as a folder.

You can see your current working directory (the one you are "in") with `pwd`.

You can change your working directory with `cd`.

```sh
$ pwd
$ cd directory_name
```

## Directory shortcuts

Several special characters are used for shortcuts in navigating the file structure. You’ll see them used often in paths.

- The single dot `.` represents the current directory.

- The double dot `..` represents the parent directory.

- The forward slash `/` by itself represents the root directory.

- The tilde `~` represents the home directory.

Try these out for yourself!

```sh
$ cd ..
$ cd ../..
$ cd /
$ cd ~
$ cd
```

## View Directory Contents

```sh
$ ls
$ ls -l
$ ls -a
$ ls -al
```

## Make and Remove Directories

```sh
$ mkdir new_directory
$ rmdir empty_directory
$ rm -rf directory_full_of_stuff # watch out!
```

## Exercise

Let’s practice using the command line! Don’t forget about using the arrow keys to find previously typed commands.

1. Navigate to your home directory

2. Create a `momentum/class` directory path

3. Navigate to that directory

4. Create a directory named `command-line` here

5. Navigate up two directories

6. Explore around your directories, viewing their contents with `ls`

7. Return to your home directory

8. Verify what your current working directory is (hint: use `pwd`)

9. Remove the `momentum/class/command-line` path

## Paths

Spaces and capitalization DO matter!

Don’t put spaces in your file or directory names. They have to be escaped when typed on the command line.

```sh
$ cd My\ Project\ Folder
$ cd my_project_folder
```

## Relative and Absolute Paths

Paths indicate the "address" of a file or directory.

```sh
$ cd projects/ruby/blackjack
$ cd /Users/myusername/code/projects/ruby/go-fish
$ cd ~/Documents/bash_commands.txt
$ cd ../study_notes
```

**Relative paths** are relative to the current working directory.

**Absolute paths** are relative to the root directory and begin with "/".

## $PATH

One or more pathnames, delimited by colons, in which to search for commands to execute.

```sh
$ echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
```

## Working with Files

```sh
$ touch new-file.txt
$ open index.html
$ cp index.html main.html
$ mv index.html ~/projects/website/index.html
$ rm new-file.txt
```

## Copy and Move Directories

```sh
$ cp -R projects portfolio
$ mv projects ~/momentum/portfolio
$ mv -i oldname newname
```

The `mv` command is useful for renaming files and directories. The `-i` option is a safeguard against an accidental overwrite.

## Viewing File Contents

```sh
$ cat ~/.bash_profile
$ tail log/development.log
$ head addresses.csv
```

## Opening a File

You can open the default text editor, or any desktop app on a Mac, from the command line.

```sh
$ open -t newfile.txt
$ open -a "Visual Studio Code" index.html
```

## Clearing the terminal

Sometimes the screen can feel cluttered. To clear your terminal screen you can:

- Type `clear` at the prompt

- `Cmd-K` on OS X

This doesn’t clear your command history; it just makes your screen look neater!

## Exercise

Let’s practice working with files from the command line.

1. Create a new directory called `cli-practice` and make that your working directory.

2. Create two text files and name them `file1.txt` and `file2.txt`. Don’t forget the file extension!

3. Open `file1.txt` in an editor and add a sentence or two to it, saving your changes.

4. Copy `file1.txt` to a third file.

5. Create a directory called `files` and move `file1.txt` into it.

6. List the contents of the `files` directory without changing your current working directory.

7. Rename `file1.txt` to `file_one.txt`

8. Remove the `files` directory without deleting `file_one.txt` first.

9. Clear your terminal!
