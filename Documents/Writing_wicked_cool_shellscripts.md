# Writing `wicked cool` shellscripts

[Basics](#Basics)

[POSIX](#POSIX?)

##### scripts

[#1 finding programs the path](##1 finding programs the path)

#### Basics

There are many different `flavours` of terminal, bash being the most popular. Many of them are universal thanks to `POSIX` however, there are some differences between a selected few. (so be careful)

You can run commands inside the terminal 

```bash
$ echo "Hello World"
```

you can run more functional commands like so

```bash
$ echo $PATH
/home/mj/scripts/:/home/mj/bin:/home/mj/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/mj/.dotnet/tools

```

> _echo_ will print these commands in the _order_ they appear in the directory

another functional command is the `which` command which prints the directory where the file, application, software, etc is located on your machine:

```bash
$ which echo
/bin/echo
```

##### calling your scripts

Before you can create a script, you need to ensure that the terminal you are using will call the scripts you are going to create on startup, or even from the _terminal_ iteself.

in order to do this you need to edit the `login script` in your _home directory_.

> OS X	=	/Users/<username>
>
> Linux	=	/home/<username>

within these directories will have a file (possibly hidden) that is called one of the following:

- _.login_
- _.profile_
- _.bashrc_
- _.bash_profile_

this depends on your system, you can discover which one it is with the following command(s):

- [ ] > _Find commands and put them here_

Once you have found the _login script_, it's advisable that you create a development directory in your home area (Simply type: **$HOME** in the terminal), this will be the are where all your scripts will be. I have named mine `scripts`. Then put the path to the directory at the top of your _login script_:

```bash
export PATH="/path/to/scripts/:$PATH"
```

This will then mean _any_ script you make in this directory will be executable in the terminal.

##### Test script

To make sure that the directory works, you can write a very simple bash script like this one:

```bash
echo "Hello World"
echo $(which neqn)
cat $(which neqn)
```

The save the file, pereferably as _intro_.

> When writting a **bash** script you don't have to place an extension at the end of the _filename_ ,**However**, if you prefer to write the extension, you write `.sh`

in the script you will notice that some _commands_ are being passed to _other commands_, like in the case of `echo $(which neqn)`. How this is done, _bash_ will run a `subshell` to run the _commands being passed as a `parameter`_. so in this case:

```sequence
title: echo $(which neqn)
participant echo
participant which
participant neqn
which->echo: echo prints which
neqn->which: which finds the path \nof the app neqn
note left of neqn: This is what\nthe subshell\nexecutes
```

once you have completed this, go to your terminal and type the following:

```bash
$ sh intro
```

your output will look like this:

```bash
Hello World
/usr/bin/neqn
#! /bin/sh
# Copyright (C) 2014 Free Software Foundation, Inc.
#
# This file is part of groff.
# 
# groff is free software; you can redistribute it and/or modify it under
# the terms of the GNU General Public License as published by the Free
# Software Foundation, either version 2 of the License (GPL2).
# 
# groff is distributed in the hope that it will be useful, but WITHOUT ANY
# WARRANTY; without even the implied warranty of MERCHANTABILITY or
# FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License
# for more details.
# 
# The GPL2 license text is available in the internet at
# <http://www.gnu.org/licenses/gpl-2.0.txt>.

# Provision of this shell script should not be taken to imply that use of
# GNU eqn with groff -Tascii|-Tlatin1|-Tutf8|-Tcp1047 is supported.

GROFF_RUNTIME="${GROFF_BIN_PATH=/usr/bin}:"
PATH="$GROFF_RUNTIME$PATH"
export PATH
exec eqn -Tascii ${1+"$@"}

# eof
```

you can make your script more _intuitive_ by applying a `Shebang` to your script.

```bash
#!/bin/bash
echo "hello world"
...
```

> a `shebang` is a definition of what _program_ you want to use to run the script you are defining
>
> if you wanted to run _`ruby`_ to run the script, then you type	-	`#!/bin/bash/ruby`
>
> if you wanted to run with _`perl`_ 						-	`#!/bin/bash/perl` 

###### Why Bash?

Bash comes pre-installed in a lot of operating systems, like Linux, Mac OSX and as of windows 10, it comes with windows too.

to give an example of how portable the bash language is, here is a `one-liner` that counts how many pages of openOfiice documents you hace

```bash
#!/bin/bash
echo "$(exiftool *.odt | grep Page-count | cut -d ":" -f2 | tr '\n' '+')""0" | bc
```



#### POSIX?

during the innovation of `unix operating systems` there was a lot of diversity in the software that was being created, and yet companies were assuring customers that all `unix OS's` were compliant with one another. the `Institute of Electrical and Electronic Engineers (IEEE)` stepped and made a standard for all `propriatery` and `open source` software followed. this standard is called the `Portable Opertating System Interface (POSIX)`. 

an Example of how this is useful is during the early days of unix being developed, the `echo` command was created differently in different unix terminals. This is awkward as all terminals should work the same. When i say some `terminals` worked _differenly_ the examples of this are mianly that different terminals would use _`-n`_ to ignore the _newline_ aspect of the echo command, where as some terminals would use _`\c`_ to ignore the new line. And things got _really_ interesting when some terminals had _echo_ as an inbuilt command which **ignored** the _-n_ and _\c_ flags and had a stand-alone binary (_/bin/echo_) which interperated the two flags. This meant that you couldn't use _echo_ in the convential way for scripting or terminal commands.

### #1 finding programs the path

The following script shows you different things about using bash script through the use of the _environmental variables_ **Mailers** and **Pager**. It shows you:

* different shell scripting techniques
* a variety of bash functions and variable slicing
* verify if a path is valid or not

```bash
#!/bin/bash
# inpath--verifies that a specified program is either valid as is, or can be found in the PATH directory list

in_Path(){
    #given a command and the PATH, this tries to find the command.
    #return 0 if found and executed
    #return 1 if otherwise
    #note: this temporarily modifies the IFS (Internal Fields Seperator) but retores it upon completion
    
    cmd=$1		outpath=$2		result=1
    oldIFS=$IFS	IFS=":"
    
    for directory in "$ourpath"
    do
    	if [ -x $directory/$cmd ] ; then
    		result=0 #if the script makes it here, it's found the command
    	fi
    done	
}


checkForCmdInPath(){
    var=$1
    
    if [ "$var" != "" ] ; then
    	if [ "${var:0:1}" = "/"] ; then
    		if [ ! -x $var ] ; then
    			return 1
    		fi
    	elif ! in_Path $var "PATH" ; then
    		return 2
    	fi
    fi
}
```

> /home/jb/Documents/scripts/scriptno1

### How it works

`checkForCmdInPath` - this function isolates the first character of a provided value to see if it is the character `/`. if it doesn't, then we know the value is a program.

`${var:0:1}` - this is a slicing function. `var` is the variable passed to it, `:0:` is the starting position of the slicing, and `:1:` is the end point of the slice, these are _inclusive_ values.

```bash
#Example of the Slicing function
$ var="Something wicked this way comes..."
$ echo ${var:10}
wicked this way comes...
$ echo ${var:10:6}
wicked
```

the script first discovers if the path passed to it has a front facing slash `/` and then continues to check whether the path passed exists on the system.

This script _assumes_ that the path passsed to it is an absolute path (because it begins with a `/`), it's easy to check if it already exists with the `-x bash operator` on line 29.

failing that, the path is then past to our `inpath` function to see if the path exists in any of the directories held within out `PATH` file.

### Running the script

```bash
if [ $# -ne 1] ; then
	echo "usage: $0 command" >&2
	exit
fi

checkForCmdInPath "$1"
case $? in
	0 ) echo "$1 found in PATH"					;;
	1 ) echo "$1 not found or not executable"	;;
	2 ) echo "$1 not found in PATH"				;;
esac

exit 0
```

This block of code needs to be ammended to the _bottom_ of the script that has been written, as it allows the script to acquire user input for the functions to be executed properly.