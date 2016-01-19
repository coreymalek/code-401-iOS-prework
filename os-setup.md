System Setup for 401 iOS
------------------

This guide will help you setup a software development environment on [Mac OS X 10.9 Mavericks](https://www.apple.com/osx/) and above. By the end, your computer will be configured with the same state-of-the-art tools used by professional software developers.

This guide is mostly compatible with older versions of Mac OS X. So follow along as best you can while Googling any problems you come across.

### The Terminal

Included in Mac OS X is the **Terminal**—an app that runs a Unix shell.

A **Unix shell** (often referred to as a "terminal") is a command line user interface between you and your computer's operating system. In a Unix shell, you can type in commands that tell the computer to do many things: navigate to files and folders, install and run programs, and change configurations. Programmers rely on their Unix shells to do lots of work, quickly and easily.

You're probably most familiar with the graphical user interface (the "GUI") of your computer's operating system. Those are the boxes, windows, and menu items that you click on with your mouse. While that's technically a shell too, most programmers think of the textual, command line interface when they hear to word _shell_.


### Explore the Terminal

Let's get our hands dirty and have some fun. First, use Spotlight to launch the Terminal app.

![](https://i.imgur.com/dvrwugy.jpg)

Once launched, you'll see something like this.

![](https://i.imgur.com/7d6GeeO.png)

Here's a quick break down of what you're seeing in the Terminal app.

| Component             | Description                            |
| --------------------- | -------------------------------------- |
| `Wed Jan 28 08:12:49` | Date of your last login                |
| `ttys003`             | Name of your last terminal session     |
| `photon`              | Name of your computer                  |
| `~` (home directory)  | Name of your working directory         |
| `ryansobol`           | Name of your user account              |
| `$`                   | Prompt symbol                          |

Any characters you type will appear after the `$` prompt symbol. Go ahead and type `uname`. After pressing the Enter key, you'll see something like this.

![](https://i.imgur.com/eGnT4NZ.png)

Here's what happened:

1. The shell waited for you to type a command.
1. You then typed the word `uname` which appeared after the prompt.
1. You pressed the Enter key which triggered the shell to accept your input.
1. The shell searched for a program called `uname`.
1. Once found, the shell launched the `uname` program and handed it control over the Terminal.
1. While running, the `uname` program told the Terminal to display the word `Darwin`.
1. Once finished, the `uname` program exited and handed control of the Terminal back to the shell.
1. The shell told the Terminal to display another prompt.
1. Once displayed, the shell began waiting for your next command.

Simply stated, a Unix shell works in a read-evaluate-print loop or **REPL**.


### Change the Terminal Profile

The default profile for the Terminal uses small, black text on a white background. Boring! Let's change that.

1. In the Terminal app, navigate to the `Terminal > Preferences` menu item.
1. In the preferences window, click the `Settings` Pane.
1. On the left side, scroll to the bottom, select the `Pro` profile, and click the `Default` button. ![](https://i.imgur.com/TQmcT8A.png)
1. Finally, quit and relaunch the Terminal.

Now, every new Terminal window will look similar to this.

![](https://i.imgur.com/87bHvEF.png)

### Install Homebrew

You may already have Homebrew installed. Let's see if you do. Type

```
which brew
```

If you get an error message, then we need to install it. Follow below to install or skip to Update Homebrew if it is installed.

Now it's time to install [Homebrew](http://brew.sh/), the de facto package manager for OS X. If you've never heard of a package manager, think of it as an App Store of **free** command line programs.

To get started, run the following command.

```
ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/install/master/install)"
```

**TIP:** Be sure to agree when asked to install the **XCode CommandLine Tools**. This takes about 30 minutes to download and install on average.


### Update Homebrew

If you've previously installed Homebrew, now's a good time to update it by running the following command.

```
brew update
```

If it's been a while since the last update, you'll see something like this.

![](https://i.imgur.com/OCAX71o.png)

Otherwise, you'll see something like this.

![](https://i.imgur.com/JPB9Gnn.png)

**TIP:** Run this command periodically as Homebrew doesn't auto-update itself. :sweat:


### Verify Homebrew

To verify Homebrew is installed correctly, run the following command.

```
brew doctor
```

And you'll see something like this.

![](https://i.imgur.com/DWfdE3D.png)

### Install Git

Check if you already have Git installed by running the following command.

```
git --version
```

You'll see something like this if it's installed. If it is, skip to Git Config, otherwise continue below.

![](https://i.imgur.com/jBSs1qR.png)

Figure out what version of OS X you are running. From the Apple menu, choose About This Mac. The version of OS X installed appears directly below “OS X.” Click the version number to see the build number. You can also use [System Information](https://support.apple.com/en-us/HT203001) to find these numbers.

![](https://support.apple.com/library/content/dam/edam/applecare/images/en_US/osx/yos_build_version.png)

If you are running:

- 10.6 Snow Leopard: download and install this: [git-*-snow-leopard](http://sourceforge.net/projects/git-osx-installer/files/git-2.3.5-intel-universal-snow-leopard.dmg/download)
	
- 10.7 Lion: download and install this [git-*-snow-leopard](http://sourceforge.net/projects/git-osx-installer/files/git-2.3.5-intel-universal-snow-leopard.dmg/download)
	
- 10.8 Mountain Lion: download and install this [git-*-snow-leopard](http://sourceforge.net/projects/git-osx-installer/files/git-2.3.5-intel-universal-snow-leopard.dmg/download)
	
- 10.9 Mavericks: download and install this [git-*-mavericks](http://sourceforge.net/projects/git-osx-installer/files/git-2.5.3-intel-universal-mavericks.dmg/download)
	
- 10.10 Yosemite: continue below
 
**NOTE:** You will need to change your install permissions to be able to install Git. The installer will prompt you to do so if necessary.

Using Homebrew, you can install Git, the version control system of choice among choosy developers.

Version control systems let programmers share and collaborate on code. With Git, multiple programmers can work on the same files, and Git keeps track of who made what changes, when. Git is usually used with a website, GitHub, that stores code (in "repositories") and lets programmers review and discuss changes before they are added. In short, Git makes everyone's lives easier.

To get started, run the following command.
```
brew install git
```

Once it is fully installed, run the following command.

```
git --version
```

And you'll see something like this.

![](https://i.imgur.com/jBSs1qR.png)

### Git Config

You're on the home stretch now! :racehorse:

Like artists, programmers sign their work. Let's configure Git to sign your commits with your name and email address.

Sign up for an account at Github [here](https://github.com).

**WARNING:** Before running the following commands, replace `YOUR FULL NAME` and `YOUR EMAIL ADDRESS` with the name and email from [your GitHub account](https://github.com/settings/profile).

```
git config --global user.name 'YOUR FULL NAME'
git config --global user.email 'YOUR EMAIL ADDRESS'
```

The terminal does not send success messages, in order to double check that you have successfully assigned your username and email: 

```
git config --list
```

Your terminal should output the following lines:

```
user.email='YOUR EMAIL ADDRESS'
user.name='YOUR FULL NAME'
```

### Congratulations!

Time for a frosty beverage. :beers:
