drupal-easier
=============

A small set of bash scripts for working with Drupal, Drush make and git.

    finddep MODULE_NAME [FIELD]

In subdirectories of the current directory, find the makefiles which
include *MODULE_NAME* and list the line with the version (or the field
specified by the optional argument *FIELD* )

    libvers

Lists the version numbers used by modules in makefiles in subdirectories.
This uses **finddep** .

    isgit
    notgit

Lists the subdirectories which are (*isgit*) or aren't (*notgit*)
git-repositories.

    setver MAKEFILE_NAME_NO_EXT MODULE_NAME MODULE_VERSION
    setver_all MODULE_NAME MODULE_VERSION

Updates the version number of *MODULE_NAME* to *MODULE_VERSION*.
**setver** requires the name of the make-file without ".make" extension
(aka the name of the file to update). Backup-files are written.
**setver_all** updates all git-repositories expecting the repository
name to match the makefile name.

    show_branch

Shows the selected git repository branch for subdirectories.

    switch_branch BRANCH

Switches the active git repository branch of all subdirectories
to BRANCH if available.

    tag2branch MAKEFILE_NAME_NO_EXT MODULE_NAME BRANCH
    tag2branch_all MODULE_NAME BRANCH

Changes version number of *MODULE_NAME* to fetch to be branch *BRANCH*
instead. Works similarly to **setver** and **setver_all**.
 
    track BRANCH

Set local branch BRANCH to track updates from/to remote ("origin")
branch BRANCH.
