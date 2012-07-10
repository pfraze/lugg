Lugg(age).sh: Take your $HOME with you
======================================

The script...

 - Creates a tmp directory
 - Checks out your dotfiles repo into it
 - Adds symbolic links of everything in the current $HOME
 - Backs up $HOME
 - Sets $HOME to the new tmp directory

Disclaimer: I'm not a pro at bash. This could be a horrible idea and I wouldn't know why. If you are a pro, and
you recognize that this is in fact a horrible idea, let me know so I can stop hurting the innocent.  

Seems to work, though.

## Usage

`source lugg.sh [repo]`

If [repo] is left off, it will revert to the original $HOME value. Example session:

```bash
~/projects/lugg$ source lugg.sh git://github.com/pfraze/dotfiles.git
Cloning into /tmp/tmp.qK7aWPam3O...
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0)
Receiving objects: 100% (3/3), done.
Home is now set to /tmp/tmp.qK7aWPam3O

/home/pfrazee/projects/lugg$ echo $HOME
/tmp/tmp.qK7aWPam3O

/home/pfrazee/projects/lugg$ source lugg.sh
Home reverted to /home/pfrazee

~/projects/lugg$ echo $HOME
/home/pfrazee
```
