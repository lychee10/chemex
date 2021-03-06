Quick install (using Mercurial)
-------------------------------
NOTE: If you don't have mercurial, yum install it!

su -c 'yum install hg -y'


1) Go to a directory where you want to put the source code,
then execute these few commands:

hg clone https://code.google.com/p/chemex/
cd ./chemex/src
INSTALL

Quick uninstall
---------------
To uninstall, all you need to do is run CLEANUP and delete all the code.
Easy! CLEANUP removes the following files:

build
~/.local/lib/python2.7/site-packages/chemex*
~/.local/bin/chemex*
chemex_dump.X folders in examples
*.pyc files

Quick update
------------
To get the latest code, you need to use Mercurial:

hg pull
hg update

The chemex code will only be updated (such that it can be run from any
directory) once you do a reinstall. This must be done in the chemex/src
directory. An INSTALL file (for Linux) is provided to run the simple
command (but may be expanded to run tests in the future).

python setup.py install --user



Configuring Authentication
--------------------------
LINUX: Once you have the clone and are added to the chemex committers, go
anywhere in the 'chemex' directory. This is where the hg commands should be
executed. Open the hidden file .hg/hgrc in this directory and add your
authentication credentials below.

WINDOWS 7: Open TurtoiseHg -> Synchronize (new option in the right-click
context menu) in one of the directories you cloned chemex.  To the left of the
path, press the little 'lock' button. In the new window add your google code
password. On the top left are your options to push and pull.

[paths]
default = https://code.google.com/p/chemex/

[ui]
username = John Doe

[auth]
chemex.prefix = https://code.google.com/p/chemex/
chemex.username = john.doe@gmail.com
chemex.password = googlepassword

The password you'll find in your Google code profile settings. It would also
be a good idea to make this file readable only by yourself.

chmod go-r hgrc



Using Mercurial (command line)
------------------------------
Aside from the first command to get the code, other commands will be
executed from within the chemex directory (ie. chemex, chemex/src,
chemex/src/examples, etc.). Tutorials can be found here as well:

http://mercurial.selenic.com/guide/

--- Getting a new clone of the repository:
hg clone https://code.google.com/p/chemex/

--- Getting updates and committing changes
- best practice will be to pull changes, update/merge your code,
  then commit the changes you made, and push

hg pull
hg update

<INSTALL and run tests> (optional, but recommended)

hg commit -m "message about changes"
hg push

--- Checking for changes in your code (wrt. checked out version)
hg summary

--- Reverting to previously checked out version
hg revert --all

--- Add/remove files to the repository
hg add <file/dir>
hg remove <file/dir>


Using Mercurial (TortoiseHg)
------------------------------
TortoiseHg works primarily with right-click context menu options and the Hg
Workbench. Everything you may want to do can be found in those menus, but
here are a couple of regular commands you may want to use.

--- Getting updates and committing changes
- best practice will be to pull changes, update/merge your code,
  then commit the changes you made, and push

Choose the Synchronize context menu while in a ChemEx directory (a similar
button can be found in the Workbench). Pull is the button at the top with a
downward arrow.  You can adjust the "Post Pull" options to automatically update.

<INSTALL and run tests &/or examples from a command prompt>

From the Hg Workbench, you can quickly get to a terminal from the Repository
menu, or by pressing Ctrl-Shift-T

Commit changes as you edit code, then return to the Synchronize menu at a later
point to Push the updates.