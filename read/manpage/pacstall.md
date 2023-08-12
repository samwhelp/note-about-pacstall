---
title: man pacstall
nav_order: 8010
has_children: false
parent: Manpage
---


# man pacstall


* [pacstall](https://github.com/pacstall/pacstall/blob/develop/pacstall)
* [pacstall.8.gz](https://github.com/pacstall/pacstall/blob/develop/misc/pacstall.8.gz)


## version

執行

``` sh
pacstall -V
```

或是執行

``` sh
pacstall --version
```

顯示

```
4.0.0 Popstar
```


## manpage

執行

``` sh
man pacstall
```

顯示

```
Pacstall(8)                 General Commands Manual                Pacstall(8)

NAME
       Pacstall - The AUR for Ubuntu

SYNOPSIS
       pacstall -V

       pacstall [-P -K -B] -I package ...

       pacstall -S term

       pacstall [-P] -R package ...

       pacstall -D package ...

       pacstall -A repository

       pacstall -U [username branch]

       pacstall -L

       pacstall [-P -K] -Up

       pacstall -Qi package [key]

       pacstall -T package

DESCRIPTION
       Pacstall  is the AUR Ubuntu wishes it had.  It takes the AUR and puts a
       spin on it, making it  easier  to  install  programs  without  scouring
       github repositories and the likes.

OPTIONS
       -h, --help
              Show the help message and exit.

       -I, --install
              Installs a given package from a repository, or a pacscript.  The
              -I flag has the ability to install packages  from  an  arbitrary
              repository,  defaulting to GitHub.  If multiple repositories are
              enabled, pacstall will  default  to  pacstall/pacstall-programs,
              but  you  can  still  choose to install from another repository.
              You can also specify a local pacscript by including  the  `.pac‐
              script'  suffix.   The  following  are  valid examples of the -I
              flag:

                     $ pacstall -I neofetch # Install neofetch

                     $  pacstall  -I   “alacritty@user/reponame”   #   Install
                     alacritty from <https://github.com/user/reponame>

                     $  pacstall -I neofetch.pacscript # Install neofetch from
                     local pacscript

       -R, --remove
              Removes a given package from system.  For example:

                     $ pacstall -R neofetch

       -S, --search
              Searches for a given package from all available repositories.  A
              clickable  hyperlink to the repositories containing the packages
              are displayed in VTE terminals.  Other repositories can be added
              using the -A flag.

                     $ pacstall -S -git # search for all git packages

                     $ pacstall -S -bin # search for all binary packages

       -A, --add-repo
              Add a given repository to pacstall.  If a plain GitHub or GitLab
              link is given without a branch, pacstall will default to master,
              but  you can specify a branch.  Local repositories are also sup‐
              ported, which can be useful for testing pacscripts without push‐
              ing  remotely, having a portable repository on a USB stick, cus‐
              tom/private applications, etc.  The following commands are valid
              ways to add a repository:

                     $ pacstall -A https://github.com/user/repo

                     $ pacstall -A https://github.com/user/repo/tree/branch

                     $ pacstall -A https://gitlab.com/user/repo

                     $ pacstall -A https://gitlab.com/user/repo/-/tree/branch

                     $  pacstall -A https://raw.githubusercontent.com/user/re‐
                     po/master

                     $ pacstall -A https://gitlab.com/user/repo/-/raw/master

                     $ pacstall -A file:///home/user/local-repository

                     $ pacstall -A /home/user/local-repository

                     $  pacstall  -A   https://myonlinerepository.com/directo‐
                     ry_containing_packagelist

       -U, --update
              Updates pacstall and needed scripts.  Arguments to this flag are
              as follows: The first flag is the  username,  while  the  second
              flag  is the branch.  The second argument is optional as long as
              the first argument is given, however both the first  and  second
              arguments  are optional together.  If no argument for the branch
              is given, it will default to master.  When updating to a specif‐
              ic repository, the arguments used will be saved so that the next
              time the -U flag is used, if no arguments  are  given,  pacstall
              will update through the same user and branch.  If there is a ty‐
              po in username or branch, pacstall will  not  update,  and  your
              current  state  will  not  be touched.  You may also replace the
              username and branch arguments with a ., which will update from a
              local Pacstall repository.  The following are valid examples:

                     $  pacstall  -U  pacstall develop # This will update pac‐
                     stall from <https://github.com/pacstall/pacstall/tree/de‐
                     velop>

                     $  pacstall  -U  pacstall:develop # This will update pac‐
                     stall from <https://github.com/pacstall/pacstall/tree/de‐
                     velop>

                     $   pacstall   -U   #  This  will  update  pacstall  from
                     <https://github.com/pacstall/pacstall/tree/develop>,  be‐
                     cause the previous arguments were saved

                     $  pacstall  -U  user  #  This  will update pacstall from
                     <https://github.com/user/pacstall/tree/master>

                     $ pacstall -U . # This will update pacstall from a  local
                     Pacstall repository

       -Up, --upgrade
              Upgrade packages that have a newer version.

       -L, --list
              List installed packages.

       -T, --tree
              Display a tree graph of a package.

       -V, --version
              Lists pacstall version and name.

       -D, --download
              Download pacscript to current directory.  You can specify an ar‐
              bitrary repository like so:

                     $ pacstall -D neofetch@user/reponame # This downloads the
                     neofetch  pacscript  from <https://github.com/user/repon‐
                     ame>

       -Qi, --query-info
              Display metadata of an installed package.  Supply a key from the
              output  to  get  it’s value.  If a key has spaces in it, replace
              them with an underscore.  For example:

                     $ pacstall -Qi neofetch install_type

       -P, --disable-prompts
              Add this flag alongside other commands to  disable  prompts  and
              accept all defaults.  For example:

                     $ pacstall -PR neofetch

       -K, --keep
              Add  this flag alongside -I and -Up to keep the build of a pack‐
              age if the build process fails or succeeds.

       -B, --build-only
              Add this flag alongside -I and -Up to just build  the  deb,  and
              not install.

ENVIRONMENT
       DISABLE_PROMPTS
              Equivalent of the -P flag.

       PACSTALL_SUPPRESS_SOLUTIONS
              Set  this  to  remove suggestions given by Pacstall to fix prob‐
              lems.

       PACSTALL_BUILD_CORES
              Set this to an integer to override the nproc command and ${NCPU}
              variable in any Pacscript.

       PACSTALL_EDITOR
              Sets the editor used by pacstall.

       PACSTALL_DOWNLOADER
              Sets  the downloading tool used.  Can be set to axel, wget, qui‐
              et-wget, or curl.

       PACSTALL_PAYLOAD
              Sets the path to a pre-downloaded package archive.

       NO_COLOR
              Turns off all colors.

FILES
       /usr/share/pacstall/repo/pacstallrepo.txt
              Repository database.

       /usr/share/pacstall/repo/update
              Saved arguments used by the -U flag.

       /usr/share/pacstall/scripts
              Assorted scripts used by pacstall to operate.

BUGS
       If you find any bugs in Pacstall itself, please submit a bug request at
       <https://github.com/pacstall/pacstall/issues>.

       If  you  find  any  bugs in a Pacscript, please submit a bug request at
       <https://github.com/pacstall/pacstall-programs/issues>.

       The main method Pacstall developers and users uses to communicate  with
       each other is through Discord (<https://discord.gg/yzrjXJV6K8>), but we
       provide a Matrix instance as  well  (<https://matrix.to/#/#pacstall:ma‐
       trix.org>).

AUTHORS
       The Pacstall team (pacstall@pm.me)

       • Elsie19

       • wizard-28

       • D-Brox

       • saenai255

       • oklopfer

       • NarutoXY

Pacstall 4.0.0 Popstar          August 05, 2023                    Pacstall(8)
```


## help

執行

``` sh
pacstall -h
```

或是執行

``` sh
pacstall --help
```

顯示

```
Usage: pacstall [-h] [-V] {-I,-S,-R,-D,-A,-U,-L,-Up,-Qi,-T} [-P] [-K] [-B]

An AUR inspired package manager for Ubuntu.

Commands:
	-I, --install <package>
		Install a package.
	-S, --search <package>
		Search for a package.
	-R, --remove <package>
		Remove a package.
	-D, --download <package>
		Download a pacscript.
	-A, --add-repo <repo>
		Add a repository.
	-U, --update [user] [branch]
		Update Pacstall.
	-L, --list
		List all installed packages.
	-Up, --upgrade
		Upgrade all installed packages.
	-Qi, --query-info <package>
		Query information about a package.
	-T, --tree <package>
		Display a tree graph of a package.

Options:
	-P, --disable-prompts
		Disable prompts.
	-K, --keep
		Keep the build files.
	-B, --build-only
		Build the deb but do not install.
	-V, --version
		Display the version number.
	-h, --help
		Display this help message.

Helpful links:
	https://github.com/pacstall/pacstall
		Official Pacstall GitHub page.
	https://github.com/pacstall/pacstall-programs/issues
		If you find a broken package, create an issue here.
	https://github.com/pacstall/pacstall/releases/latest
		Link to the latest release of Pacstall.
```
