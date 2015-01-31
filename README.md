dotfiles
========

Configs for Linux. I mostly use obenbox, so that is what you will find here as well. 
Wallpapers can not be found here due to unclear licenses.

## Install

There is an install script that takes an install list and can either link (default) or copy
the dotfiles. The install list is simply a tab separated file with the path to the dotfile
from the executed directory followed by a tab and the directory relative to your home directory 
where the files will be installed. Sounds hard, but is quite simple for instance take the following
installation list:

**install.lst**:
```
.tmux.conf  .
.vimrc  .
openbox/rc.xml  .config/openbox
```

Executing `./install install.lst l` will create the following links
```
/home/you/.tmux.conf -> /path/to/git_directory/.tmux.conf
/home/you/.vimrc -> /path/to/git_directory/.vimrc
/home/.config/openbox/rc.xml -> /path/to/git_directory/openbox/rc.xml
```

If you pass c in place of l files will be copied and not linked (preferred for files you will have to adapt).


## Additional Subfolders

* psmouse-elantech-v7right
  Contains a fixed kernel module for Elanteck trackpads with a missing right click.
* scripts
  Contains some terminal color scripts. Ghosts script courtesy of [homosexualobster](https://github.com/homosexualobster/dotfiles)
