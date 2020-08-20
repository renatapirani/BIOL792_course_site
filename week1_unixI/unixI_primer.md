# Unix primer 1

## topics to cover
- getting set with Unix
- Text editors: why they are important, choosing among options
- introduction to simple Unix commands
- From the book: Chapter 1; Chapter 4 to page 61. Preview chapters 2 and 3 if you like, we will cover regular expressions in depth once we get into Python.

Here we will  get set up for the course. First, making sure everyone has Unix or Linux running on their computers. Second, getting everyone comfortable choosing a text editor to use for this course and for writing and editing code in general.

We will then get started on learning useful basic Unix commands which you are likely to use over and over and over again. We will gain deeper familiarity with the directory structure, how to navigate through this structure, view contents of directories and files, and learn to make, copy, or delete files and directories.

## Text display in these primers

Text that is meant to serve as an example for what to type into a terminal window or into python scripts will be indented and highlighted straight form text as below. So when you see this, you are seeing text that in many cases can be copied and pasted, for example, into your terminal window. 

       $ ls -lrh

Unix or Python commands, functions, or variables will also be designated in similar font when written. For example, `man`, `pwd` and `wc` are among the first Unix commands we will learn.

## Where can you run Unix?

If you have an apple computer, you already own a unix machine. Just go into the Utilities directory, within the Application directory, and you will find the Terminal app. I suggest dragging that to your dock or wherever you organize applications you use frequently. For this class, having a mac computer will be the easiest way forward as your computer is ready to go and the examples in the book are written as unix on mac computers. For a brief history of Unix and its significance, as well as an alternative introduction to basic commands and ideas, see [Unix primer](https://github.com/tparchman/BIOL792/blob/master/unix_resources/unix_buerkle_guide.pdf) written by Alex Buerkle at University of Wyoming.

If you use a windows computer a bit of adjustment will be necessary, but you have several options. You can Install Cygwin — this provides a Linux-like environment on your PC. Alternatively, and preferably, you can [install ubuntu](https://practicalcomputing.org/ubuntu.html) linux alongside or within your windows operating system. **Appendix 1** of Haddock and Dunn explains in general detail how to install ubuntu linux on an windows operating system using a virtual machine.

## Big data: text processing and manipulation
Most big data is stored as text, or compressed text files. Text is special  binary format of storing data whose numbers correspond to human readable digits, letters or characters. This is the most transparent and transportable way to store data, and is hence the medium of big data. 

In addition, computer code is written in text. In this course we will write Bash and Python scripts, which will simply be written and stored in text files interpretted by the appropriate mechanism and executed through your terminal.

## Text editors for writing and storing code

Programs are typically just text files; they contain text written commands for 	operations, functions, input/output, etc. Microsoft Office documents or other word processing applications are NOT plain text files, and we will NOT be using any such applications. 

Text editors for working with data or programming fill several necessities for data science.

- They are empowered with tools for the searching and manipulation of data. For example, any worthy text editor is equipped with mechanisms for searching/replacing data based on flexible pattern matching. The representation of such patterns, otherwise known as **regular expressions** is a major feature of TextWrangler and other editors, and is also a major component of programming in Python or other scripting languages.

- Text editors  have syntax recognition which colors text with different functions and purposes accordingly. This is invaluable for troubleshooting code. Common text editors include `TextWrangler`, `Visual Studio Code`, `Sublime`, `Emacs`, `VIM`. I suggest `TextWrangler` for this course because your book utilizes this editor, and because it employes keyboard shortcuts as you are likely accustomed (Emacs and VI are very popular, but youd have to learn new keyboard shortcuts). You should install and be comfortable with one before the next class.

- Line endings are encoded differently for different files from different operating systems, and this can represent a stumbling block during the first weeks of learning to manipulate data with Unix and Python. Read pages 13-14 of Haddock and Dunn carefully to understand this issue, and for a quick fix in TextWrangler. We will always want to be working with Unix line endings

Example syntax highlighting (note this is Perl, not Python or unix)

![syntax_image](https://github.com/tparchman/BIOL792/tree/master/images/syntax_eg.png)



## Unix first steps: getting set with the terminal

We will use the terminal for navigating and manipulating files and directories, executing Unix commands, and executing code written in Python of Bash. Conveniently, you will also use the same terminal windows to execute such work on remote servers or HPC (High Performance Computing) systems. In general, we will learn how to use the terminal to increase efficiency in handling, manipulating, and analyzing large data.

If you have a mac, go into the Utilities directory, within the Application directory, and you will find the Terminal app. I suggest dragging that to your dock or wherever you organize applications you use frequently. See appendix 1 of Haddock and Dunn for orienting in Unix from a Windows OS.

You can have as many terminal windows open at a time as like, and you can customize the look and behavior of the terminal. For example:


- make the text larger/smaller (hold down ‘command’ and either ‘+’ or ‘–’)
- have multiple terminal windows on screen ('command n')
- See terminal preferences for appearance and behavior options


## Basic Unix commands

Open a terminal window and try the commands below. Make a practice directory, a few practice text files, and experiment with navigating up and down, creating files and directories, and copying and moving them These are just some examples of most commonly used commands for navigating the filesystem, copying and moving files. You will see `ls` simply lists the contents of the directory you are in.
 

     $ ls

Most Unix commands also have command line options, or **arguments**, which follow `-` after the command. Try `ls` below with the additional options h or l, which could be specified in either format shown below

    $ ls -l -h
    $ ls -lh

*an **argument** is anything, generally speaking, specified after a command or executable script. It could be a command line option as above, or it could be a file meant to be processed by a Python, Bash, or Perl script.

You can move around directories using the `cd` command

    $ cd [name of directory within the directory you are in]

To move up a directory

    $ cd ../

To move up two directories, and so on

    $ cd ../../

To make a new text file

    $ touch test1.txt

To copy that file to the directory above

    $ cp test1.txt ../

To move that file to the directory above

    $ mv test1.txt ../

The current, or working directory, is simply indicated by `.`. So to move the file that you moved up one directory with the previous command back to the directory you are in

    $ mv ../test1.txt .

To pring to screen the directory you are working in (working directory)

    $ pwd 

To make a new directory

    $ mkdir DNAseq

To remove that same directory

    $ rmdir DNAseq

**NOTE on EXTREME CAUTION**: removing files or directories in Unix requires caution. There is no second chance, not intermediate trash or recyclng bin. We will discuss in further detail next week. You will see when using the base commands `rm` and `rmdir` you are prompted about whether you are sure you want to remove. We will talk about why we might want to turn that prompt off, and when, and when not, later. For now just be forewarned that with the right combination of as few as 7 keystrokes you could send your entire system into the ether.

## Unix directory tree

The Unix directory tree is heirarchical and simple to navigate. The more you use your terminal to navigate your file system, the more you will realize how much time you waste using your mouse and an application such as finder or windows explorer. Eventually you will accept the fact that the terminal is a much much faster way to move around your system, and will hopefully make that transition in the name of efficiency. The Unix file system:

![unixtree](https://github.com/tparchman/BIOL792/tree/master/images/unixtree.png)


root is the top of the tree, all other directories reside within root. You can move to root anytime by:

    $ cd /

Unix systems are multi-user. When you login with a username and password, you have your own home directory that resides at /Users/. You can move directly to your home directory from anywhere with the two shortcuts below.

    $ cd ~

    $ cd 

## Path

This is a representation of where something is located that includes all of the directories from root down to location. The example below indicates the `path` from root to a "python_resources_modules" directory.

    $ /Users/tparchman/Desktop/files/python_resources_modules

`pwd` can always be used to tell you where you are, and will print out the **absolute** path, and you can use either absolute or relative paths to `cp`, `mv`, or to provide input or output for any unix command. You can use `../` or `../../` as **relative** path information for moving up, or something like `cp file1.txt /output/Rcode/`, where you are moving the file from the current directory to an output/Rcode/ **relative** path within that directory.

## `man` pages and command line options
For any Unix command (there are currently **281,555**!) you can find the full information on that command by using  `man`.

For example:

    $ man pwd
will tell you what `pwd` does.

Try:

    $ man grep

Here you will see the information on grep displayed in a text viewer called `less`. You can move forward one page at a time with the space bar. Upon scrolling through the `grep` `man` page, you will see that grep has many command options and is a flexible, powerful, and commonly used text processing tool.

As man pages will typically be viewed with `less`, look at the man page for `less` for guidance on how to control this text viewer

    $ man less

You will not that space bar advances a page, `b` scrolls backwards a page. Pattern matches can be specified after typing `/`. 

Most Unix commands also have command line options, which follow `-` after the command. Try `ls` below with the additional options h or l, which could be specified in either format shown below

    $ ls -l -h
    $ ls -lh

Now, notice that when you use `man`, all of the command line options will be clearly listed and efficiently described. Try the below for command line option explanations for `ls`.

    $ man ls

**Online manual pages**, and other sites are also plentiful to read up on unix commands or if you are looking for tricks

## Working efficiently in the terminal (your mouse is useless)

**TAB autocomplete**: Now that you have played around with some basic commands, you probably realized that typing mistakes slow you down. Luckily, you dont have to type much, because upon hitting the tab key, your terminal will autocomplete as far as it can. In fact, this function is so useful, that tab will be among the keys you use most. for this:


**Terminal shortcuts**: Up and Down arrows will allow you to scroll through previous commands that have been typed from the terminal. This is very useful

You can not use your mouse to move the terminal cursor. 

- “control a” will move the cursor to the beginning of what you have typed.

- “control e” will move the cursor to the end of what you have typed.

- “control l” will clear one line at a time