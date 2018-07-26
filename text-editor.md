# Text editor

## vi
**vi** is a text editor in Linux. You can use keyboard and mouse to finish your most text work.

> **vim** full name is  _**Vi IMproved**_. They are same one, but near.

### Enter vi Text Editor
You can enter vi by next way:
``vi filename``, If file no exist ,vi will creat a file.

```
$vi testfile
|
~
~
~
~
~
~
~
"testfile" [New File]
```

### Vi modes
vi have two modes 

* command mode
* insert mode

In command mode, the letters of the keyboard perform editing functions (like moving the cursor, deleting text, etc.). Switch to insert mode ,please enter ``<i>`` key.

In insert mode, the letters you type form words and sentences. Unlike many word processors, vi starts up in command mode. If you are in insert mode and want back to command mode, press the escape ``<Esc>`` key.

### Quit vi

You can quit vi in command mode. First, make sure the vi in command mode.And, you can use ``:q`` to quit the vi. If you meet problem the ``:q!`` will help you out of vi without quit.And if you want to save your writed text, press ``:wq`` to save and quit the text.


### Here is a list to show all command in vi

| Command  | Description   |
| :---     | :---          |
| :w       | save the file |
| :q       | quit the vi   |
| :wq      | quit and save the file |
| ZZ       | it is equal to `:wp` and you should care about the `Z` is capital letter  |

## NANO

Nano is a another one text editor work in linux. It not preinstall in all Linux realse,but it easy to use.

Like the vi, you can use ``nano filename`` to create a file or edit it. When you enter the world of nano, you will find the different from it and vi. Under the screen, you will see a bar. The ``^`` is mean that you can use ``Ctrl`` + ``<key>``to use it. For example, you can use ``Ctrl`` + ``o`` to save the file. And you can quit nano use ``Ctrl`` + ``X``. If you want get more infomation about nano, press the ``Ctrl`` + ``G`` get the help.