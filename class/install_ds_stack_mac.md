(page_install_ds_stack_macOS)=
MDS software stack install instructions for macOS
=======================

<!-- Open links in a new tab unless they have the `` attribute -->
<head>
    <base target="_blank">
</head>

```{important} 
This guide has been (lightly) adapted from the UBC-Vancouver [MDS Install stack](https://ubc-mds.github.io/resources_pages/installation_instructions/) under a CC-BY-SA 4.0 license.
```

These instructions will walk you through installing the required Data Science software stack for the UBC Master of Data Science program. Before starting, ensure that your laptop meets our program requirements:

 - runs one of the following operating systems: macOS 10.15.X (Catalina), Ubuntu 20.04, Windows 10 Professional, Enterprise or Education; version 2004.
    - **Windows 10 Home is not sufficient** as not all the software required for the program can be installed on that OS. [Click here to download Windows 10 Education for free from UBC.](https://it.ubc.ca/software-downloads)
    - When installing Ubuntu, checking the box "Install third party..." will (among other things) install proprietary drivers, which can be helpful for wifi and graphics cards.
- can connect to networks via a wireless connection
- has at least 50 GB disk space available
- has at least 8 GB of RAM
- uses a 64-bit CPU
- is at most 6 years old at the start of the program (4 years old or newer is recommended)
- uses English as the default language
- student user has full administrative access to the computer

**Students' whose laptops do not meet the requirements specified above will not be able to receive technical assistance from the MDS team in troubleshooting installation issues.**

## Table of Contents

- [UBC Student Email](#ubc-student-email)
- [Web browser](#web-browser)
- [LastPass password manager](#lastpass-password-manager)
- [Slack](#slack)
<!-- - [Bash shell](#bash-shell) -->
- [Visual Studio Code](#visual-studio-code)
- [VS Code extensions](#vs-code-extensions)
- [GitHub](#github)
- [Git](#git)
- [Python, Conda, and JupyterLab](#python-conda-and-jupyterlab)
- [Essential python packages](#essential-python-packages)
- [JupyterLab setup](#jupyterlab-setup)
- [R, XQuartz, IRkernel, and RStudio](#r-xquartz-irkernel-and-rstudio)
- [LaTeX](#latex)
- [PostgreSQL](#postgresql)
- [Docker](#docker)
- [Post-installation notes](#post-installation-notes)

## Installation notes

If you have already installed Git, Latex, or any of the R or Python related packages
please uninstall these and follow the instructions below to reinstall them
(make sure to also remove any user configuration files and backup them if desired).
In order to be able to support you effectively
and minimize setup issues and software conflicts,
we require all students to install the software stack the same way.

In all the sections below, if you are presented with the choice to download either a 64-bit (also called x64)
or a 32-bit (also called x86) version of the application **always** choose the 64-bit version.

Once you have completed these installation instructions, make sure to follow the post-installation notes at the end to check that all software is setup correctly.

## UBC Student Email
Please sign up for a UBC Student Email. This account will also grant you access to a range of UBC services, including Microsoft Teams and OneDrive. To do so navigate to [https://it.ubc.ca/services/email-voice-internet/ubc-student-email-service](https://it.ubc.ca/services/email-voice-internet/ubc-student-email-service) and follow the instructions under "Get Started". 

## Web browser

In MDS we will be using many tools that work most reliably on Google Chrome and Firefox (including our online quiz software), so we recommend that you use one of these browsers.

- To install Chrome, go to [https://www.google.com/chrome/](https://www.google.com/chrome/), click on "Download Chrome" and follow the instructions on the website to finish the installation.
- To install Firefox, go to [https://www.mozilla.org/en-US/firefox/new/](https://www.mozilla.org/en-US/firefox/new/), click on "Download Firefox" and follow the instructions on the website to finish the installation.

## LastPass password manager

Some MDS courses (e.g. the capstone project) use the LastPass password manager to share credentials. Although we will not cover privacy and security topics until the second semester of the program, we recommend that you use a password manager such as LastPass to help you create strong passwords and store them securely, and to facilitate online authentication. You can sign up for a free LastPass account here: [https://lastpass.com/create-account.php](https://lastpass.com/create-account.php). We also recommend installing the LastPass Chrome or Firefox browser extension available here: [https://lastpass.com/misc_download2.php](https://lastpass.com/misc_download2.php).

## Slack

For our MDS courses and program announcements, correspondence and course forums we use the communication tool Slack. Slack can be accessed via the web browser, however we strongly recommend installing the Slack App. The Slack app can be installed from the Mac App Store, or from the Slack website. Installation instructions from the Slack website install method are here: [https://slack.com/intl/en-ca/help/articles/207677868-Download-Slack-for-Mac](https://slack.com/intl/en-ca/help/articles/207677868-Download-Slack-for-Mac)

<!-- Disagree with this recommendation, Zsh is perfectly fine.
## Bash shell

Apple recently changed the Mac default shell in the Terminal to Zsh, however, we aim to teach with the same shell across all three operating systems we support, which is the Bash shell. Thus, we ask that you change the default shell in your Terminal to Bash by opening the Terminal ([how to video](https://youtu.be/5AJbWEWwnbY)) and typing:

```
chsh -s /bin/bash
```

You will have to quit all instances of open Terminals and then restart the Terminal for this to take effect.
-->

## Enhance your Terminal shell

Apple recently changed the Mac default shell in the Terminal to Zsh - though the [reasons for this](https://thenextweb.com/dd/2019/06/04/why-does-macos-catalina-use-zsh-instead-of-bash-licensing/) are complicated, it is a huge improvement over the out-dated Bash version that came pre-installed on macOS.

To make sure your shell is set to Zsh, open up your terminal and run this command:

```
chsh -s path
```

### [Optional] Install Ohmyzsh to get terminal colours, and highlighting

Oh My Zsh is installed by running the following command in your Terminal: 

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

You may now customize your Terminal with themes by [following the directions here](sh -c "https://github.com/ohmyzsh/ohmyzsh#selecting-a-theme".

## Visual Studio Code

### Installing

The open-source text editor Visual Studio Code (VS Code) is both a powerful text editor and a full-blown Python IDE, which we will use for more complex analysis.
You can download and install the macOS version of VS Code from the VS code website [https://code.visualstudio.com/download](https://code.visualstudio.com/download).
Once the download is finished, click "Open with Archive utility", and move the extracted VS Code application from "Downloads" to "Applications".

### Launch from the Terminal (aka command line)

1. Launch VS Code.
2. Open the Command Palette (⇧⌘P ; shift+command+P).
3. Type 'shell command' to find the "Shell Command: Install 'code' command in PATH" command.
4. Hit Enter
5. Restart the terminal for the new $PATH value to take effect. 

You can open files in VS Code from the Terminal!
Alternatively, just type `code .` in any folder to start editing files in that folder.

You can test that VS Code is installed and can be opened from Terminal by restarting terminal and typing the following command in a Terminal:

```
code --version
```

you should see something like this if you were successful:

```
1.48.2
a0479759d6e9ea56afa657e454193f72aef85bd0
x64
```

[Manual install instructions are here, but remember you're using the zsh now!](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line) steps as well.

### VS Code extensions

The real magic of VS Code is in the extensions that let you add languages, debuggers, and tools to your installation to support your specific workflow. Now that we have installed all our other Data Science tools, we can install the VS Code extensions that work really well with them. From within VS Code you can open up the [Extension Marketplace (read more here)](https://code.visualstudio.com/docs/editor/extension-gallery) to browse and install extensions by clicking on the Extensions icon in the Activity Bar indicated in the figure below.

<img src="../images/vscode.png" alt = ""/>

To install an extension, you simply search for it in the search bar, click the extension you want, and then click "Install". There are extensions available to make almost any workflow or task you are interested in more efficient! Here we are interested in setting up VS Code as a Python IDE. To do this, search for and install the following extensions:

- Python (everything Python: notebooks, debugging, linting, formatting, etc.)
- markdownlint (markdown linting and style checking extension)
- GitLens - Git supercharged (powerful extension that extends VS Code's native git capabilities)
- Docker (easily use Docker from VS Code)
- (Optional) Material Theme and/or Predawn Theme Kit (additional colour themes to choose from)
- (Optional) Material Icon Theme (great-looking custom file icons!)
- (Optional) Bracket Pair Colorizer 2 (add colour to help distinguish your brackets: (), [], {})

[This video tutorial](https://www.youtube.com/watch?v=06I63_p-2A4) is an excellent introduction to using VS Code in Python.


## GitHub.com

In MDS we will use the publicly available [GitHub.com](https://github.com/). Please follow the set-up instructions for both below.

Sign up for a free account at [GitHub.com](https://github.com/) if you don't have one already.

<!--
### GitHub.ubc.ca

To add you to the MDS organization on [Github.ubc.ca](https://github.ubc.ca) we need you to login to [Github.ubc.ca](https://github.ubc.ca) using your CWL credentials.

This step is required for
- being able to store your work
- all homework submission and grading
- working collaboratively
-->

## Git

We will be using the command line version of Git as well as Git through RStudio and JupyterLab. Some of the Git commands we will use are only available since Git 2.23, so if you're Git is older than this version, we ask you to update it using the Xcode command line tools (not all of Xcode), which includes Git.

Open Terminal and type the following command to install Xcode command line tools:

```
xcode-select --install
```

After installation, in terminal type the following to ask for the version:

```
git --version
```

you should see something like this (does not have to be the exact same version) if you were successful:

```
git version 2.24.2 (Apple Git-127)
```

> Note: If you run into trouble, this is the time to post on Piazza with your error message and ask for help! You can also see the Install Git > Mac OS section from [Happy Git and GitHub for the useR](http://happygitwithr.com/install-git.html#mac-os) for additional help or strategies for Git installation.

### Configuring Git user info

Next, we need to configure Git by telling it your name and email. To do this type the following into the terminal (replacing Jane Doe and janedoe@example.com, with your name and email (the same used to sign up for GitHub), respectively):

```
git config --global user.name "Jane Doe"
git config --global user.email janedoe@example.com
```

> Note: to ensure that you haven't made a typo in any of the above, you can view your global Git configurations by either opening the configuration file in a text editor (e.g. via the command `code ~/.gitconfig`) or by typing `git config --list --global`.

### Setting VS Code as the default editor

To make programs run from the terminal (such as `git`) use VS Code by default, we will modify `~/.z_profile`. First, open it using VS Code:

```
code ~/.z_profile
```

> Note: If you see any existing lines in your `~/.z_profile`
> related to a previous Python or R installation,
> please remove these.

Append the following lines:

```
# Set the default editor for programs launch from terminal
EDITOR="code --wait"
VISUAL=$EDITOR  # Use the same value as for "EDITOR" in the line above
```

Then save the file and exit VS Code.

> Most terminal programs will read the `EDITOR` environmental variable when determining which editor to use, but some read `VISUAL`, so we're setting both to the same value.

## Python, Conda, and JupyterLab

### Python and Conda

We will be using Python for a large part of the program, and `conda` as our Python package manager. To install Python and the `conda` package manager, we will use the [Miniconda platform (read more here)](https://docs.conda.io/en/latest/miniconda.html), which [Miniconda MacOSX 64-bit pkg install for Python **3.8** can be downloaded here.](https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.pkg).

After installation, restart the terminal. If the installation was successful, you will see `(base)` prepending to your prompt string. To confirm that `conda` is working, you can ask it which version was installed:
```
conda --version
```
which should return something like this:

```
conda 4.8.2
```

> Note: If you see `zsh: command not found: conda`, see the section on [Bash](#bash-shell) above to set your default Terminal shell to Bash as opposed to Zsh.

Next, type the following to ask for the version of Python:
```
python --version
```
which should return something like this:

```
Python 3.8.3
```

> Note: If instead you see `Python 2.7.X` you installed the wrong version. Uninstall the Miniconda you just installed (which usually lives in the `/opt` directory), and try the installation again, selecting **Python 3.8**.

## Essential Python packages

`conda` installs Python packages from different online repositories which are called "channels".
A package needs to go through thorough testing before it is included in the default channel,
which is good for stability,
but also means that new versions will be delayed and fewer packages are available overall.
There is a community-driven effort called the [conda-forge (read more here)](https://conda-forge.org/),
which provides more up to date packages
To enable us to access the most up to date version of the Python packages we are going to use,
we will add the more up to date  channel,
To add the conda-forge channel by typing the following in the terminal:


```
conda config --add channels conda-forge

```

To install packages individually, we can now use the following command: `conda install <package-name>`. Let's install the key packages needed for the start of our program:

```
conda install \
 jupyterlab=2.* \
 numpy=1.* \
 pandas=1.* \
 flake8=3.* \
 black=19.*
```

`conda` will show you the packages that will be downloaded,
and you can press enter to proceed with the installation.
If you want to answer `yes` by default and skip this confirmation step,
you can replace `conda install` with `conda install -y`.

> Note: we will use many more packages than those listed above across the MDS program, however we will manage these using virtual environments (which you will learn about in DSCI 521: Platforms for Data Science).

## JupyterLab setup

We will be using the Jupytext Python package and the JupyterLab git extension to facilitate using Jupyter notebooks with Git & GitHub. Install them via the following commands:

```
conda install nodejs=10.*
pip install --upgrade jupyterlab-git
conda install jupytext=1.*
jupyter lab build
```

To test that your JupyterLab installation is functional, you can type `jupyter lab` into a terminal, which should open a new tab in your default browser with the JupyterLab interface.
To exit out of JupyterLab you can click `File -> Shutdown`,
or go to the terminal from which you launched JupyterLab and hold `Ctrl` while pressing `c` twice.

## R, XQuartz, IRkernel, and RStudio

R is another programming language that we will be using a lot in the MDS program. We will use R both in Jupyter notebooks and in RStudio.

### R

Go to [https://cran.r-project.org/bin/macosx/](https://cran.r-project.org/bin/macosx/) and download the latest version of R for Mac (Should look something like this: R-3.6.1.pkg). Open the file and follow the installer instructions.

After installation, in Terminal type the following to ask for the version:
```
R --version
```

You should see something like this if you were successful:

```
R version 4.0.0 (2020-04-24) -- "Arbor Day"
Copyright (C) 2020 The R Foundation for Statistical Computing
Platform: x86_64-apple-darwin17.0 (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under the terms of the
GNU General Public License versions 2 or 3.
For more information about these matters see
https://www.gnu.org/licenses/.
```

> Note: Although it is possible to install R through conda, we highly recommend not doing so. In case you have already installed R using conda you can remove it by executing `conda uninstall r-base`.

### XQuartz

Some R packages rely on the dependency XQuartz which no longer ships with the Mac OS, thus we need to install it separately. Download it from here: [https://www.xquartz.org/](https://www.xquartz.org/) and follow the installation instructions.

### RStudio

Download the macOS Desktop version of RStudio Preview from [https://rstudio.com/products/rstudio/download/preview/](https://rstudio.com/products/rstudio/download/preview/). Open the file and follow the installer instructions.

To see if you were successful, try opening RStudio by clicking on its icon (from Finder, Applications or Launchpad). It should open and look something like this picture below:

<img src="../images/RStudio.png" alt = ""/>


### Essential R packages

Next, install the key R packages needed for the start of MDS program,
by opening up RStudio and
typing the following into the R console inside RStudio:

```
install.packages(c('tidyverse', 'blogdown', 'xaringan', 'renv', 'usethis', 'devtools'))
```

> Note: we will use many more packages than those listed above across the MDS program, however we will manage these using the `renv` package manager (which you will learn about in DSCI 521: Platforms for Data Science).

### IRkernel

The `IRkernel` package is needed to make R work in Jupyter notebooks. To enable this kernel in the notebooks, install by pasting the following command into the RStudio Console:

```
install.packages('IRkernel')
```

Next, open a terminal and type the following
(you can't use RStudio for this step
since it doesn't honor `$PATH` changes in `~/.z_profile`)

```
R -e "IRkernel::installspec()"
```

To see if you were successful, try running JupyterLab and check if you have a working R kernel. To launch the JupyterLab type the following in Terminal:

```
jupyter lab
```

A browser should have launched and you should see a page that looks like the screenshot below. Now click on "R" notebook (circled in red on the screenshot below) to launch an JupyterLab with an R kernel.

<img src="../images/jupyter_lab_r_kernel.png" alt = ""/>

Sometimes a kernel loads, but doesn't work as expected. To test whether your installation was done correctly now type `library(tidyverse)` in the code cell and click on the run button to run the cell. If your R kernel works you should see something like the image below:

<img src="../images/jupyter_lab_r_kernel2.png" alt = ""/>

To improve the experience of using R in JupyterLab,
we will add an extension that allows us to setup keyboard shortcuts for inserting text
(thanks to former MDS student Ryan Homer for developing this extension!).
By default,
it creates shortcuts for inserting two of the most common R operators: `<-` and `%>%`.
Run the following from terminal to install the extension:

```
jupyter labextension install @techrah/text-shortcuts
jupyter lab build
```

To check that the extension is working,
open JupyterLab,
launch an R notebook,
and try inserting the operators by pressing `Alt` + `-` or `Shift` + `Command` + `m`, respectively.

## LaTeX

We will install the lightest possible version of LaTeX and it's necessary packages as possible so that we can render Jupyter notebooks and R Markdown documents to html and PDF. If you have previously installed LaTeX, please uninstall it before proceeding with these instructions.

First, open RStudio and run the following commands to install the `tinytex` package and setup `tinytex`:

```
install.packages('tinytex')
tinytex::install_tinytex()
```

> Note: You might be asked to enter your password during installation.
> If you see an error message towards the end of the installation
> telling you that `/usr/local/bin` is not writeable,
> you will need to open a terminal and run the following two commands before proceeding:
>
>```
> sudo chown -R $(whoami):admin /usr/local/bin
> ~/Library/TinyTeX/bin/x86_64-darwin/tlmgr path add
>```

You can check that the installation is working by opening a terminal and asking for the version of latex:

```
latex --version
```

You should see something like this if you were successful:

```
pdfTeX 3.14159265-2.6-1.40.21 (TeX Live 2020)
kpathsea version 6.3.2
Copyright 2020 Han The Thanh (pdfTeX) et al.
There is NO warranty.  Redistribution of this software is
covered by the terms of both the pdfTeX copyright and
the Lesser GNU General Public License.
For more information about these matters, see the file
named COPYING and the pdfTeX source.
Primary author of pdfTeX: Han The Thanh (pdfTeX) et al.
Compiled with libpng 1.6.37; using libpng 1.6.37
Compiled with zlib 1.2.11; using zlib 1.2.11
Compiled with xpdf version 4.02
```

The above is all we need to have LaTeX work with R Markdown documents, however for Jupyter we need to add several more packages. Do this by opening a terminal and copying the following there press enter:

```
tlmgr install eurosym \
  adjustbox \
  caption \
  collectbox \
  enumitem \
  environ \
  fp \
  jknapltx \
  ms \
  parskip \
  pgf \
  rsfs \
  tcolorbox \
  titling \
  trimspaces \
  ucs \
  ulem \
  upquote
```

To test that your latex installation is working with jupyter notebooks,
launch `jupyter lab` from a terminal and open either a new notebook
or the same one you used to test IRkernel above.
Go to `File -> Export notebook as... -> Export Notebook to PDF`.
If the PDF file is created,
your LaTeX environment is set up correctly.

## PostgreSQL

We will be using PostgreSQL as our database management system. You can [download PostgreSQL 12.4 from [here](https://www.enterprisedb.com/downloads/postgresql) (do *not* select version 13). Follow the instructions for the installation. In the password page, type whatever password you want, but make sure you'll remember it later. For all the other options, use the default. You do not need to run "StackBuilder" at the end of the installation (if you accidentally launch the StackBuilder, click "cancel", you don't need to check any boxes).

To test if the installation was successful open the `SQL Shell` app from the LaunchPad or applications directory. You will be asked to setup your configuration, accept the default value (the one within square brackets) for the first four values by pressing enter four times, then type in your password and press enter one last time. It should look like this if it is working correctly:

<img src="../images/psql-mac.png" alt = ""/>

## Docker

You will use Docker to create reproducible, sharable and shippable computing environments for your analyses. For this you will need a Docker account. You can [sign up for a free one here](https://store.docker.com/signup?next=%2F%3Fref%3Dlogin).

After signing-up and signing into the Docker Store, go here: [https://store.docker.com/editions/community/docker-ce-desktop-mac](https://store.docker.com/editions/community/docker-ce-desktop-mac) and click on the "Get Docker" button on the right hand side of the screen. Then follow the installation instructions on that screen to install the stable version.

To test if Docker is working, after installation open the Docker app by clicking on its icon (from Finder, Applications or Launchpad). Next open Terminal and type the following:
```
docker run hello-world
```
you should see something like this if you were successful:

```
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete 
Digest: sha256:451ce787d12369c5df2a32c85e5a03d52cbcef6eb3586dd03075f3034f10adcd
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```
## Post-installation notes

You have completed the installation instructions, well done 🙌!
We have created a script to help you check that your installation was successful,
and to provide instructions for how you can troubleshoot any potential issues.
To run this script,
please execute the following command from your terminal.

```
bash <(curl -Ss https://raw.githubusercontent.com/UBC-MDS/UBC-MDS.github.io/master/resources_pages/check-setup-mds.sh)
```

The output from running the script will look something like this:

````
# MDS setup check 0.1.0

If a program or package is marked as MISSING,
this means that you are missing the required version of that program or package.
Either it is not installed at all or the wrong version is installed.
The required version is indicated with a number and an asterisk (*),
e.g. 4.* means that all versions starting with 4 are accepted (4.0.1, 4.2.5, etc).

You can run the following commands to find out which version
of a program or package is installed (if any):
```
name_of_program --version  # For system programs
conda list  # For Python packages
R -q -e "installed.packages()[,c(Package, Version)]"  # For R packages
```

Checking program and package versions...

## Operating system
ProductName:    Mac OS X
ProductVersion: 10.15.5
BuildVersion:   19F101

## System programs
OK        psql 12.3
MISSING   rstudio=1.*
OK        R 4.0.2 (2020-06-22) -- "Taking Off Again"
OK        python 3.8.3
OK        conda 4.8.3
OK        bash 4-pc-linux-gnu)
OK        git 2.27.0
OK        make 4.3
OK        latex 3.14159265-2.6-1.40.21 (TeX Live 2020)
OK        tlmgr 55369 (2020-06-01 02:32:00 +0200)
MISSING   docker=19.*
MISSING   code=1.*

## Python packages
MISSING   jupyterlab=2.*
MISSING   numpy=1.*
MISSING   pandas=1.*
OK        flake8=3.7.9
MISSING   black=19.*
MISSING   nodejs=10.*
OK        jupytext=1.3.4
MISSING   jupyterlab-git=0.*
MISSING   jupyterlab PDF-generation failed. Check that latex and jupyterlab are marked OK above.

## R packages
OK        tidyverse=1.3.0
OK        blogdown=0.20
OK        xaringan=0.16
OK        renv=0.11.0
OK        IRkernel=1.1.1
OK        tinytex=0.25
OK        rmarkdown PDF-generation was successful

This output and additional configuration details
have been saved to the file check-setup-mds.log in this directory.
````

As you can see at the end of the output,
a log file is saved in your current directory.
We might ask you to upload this file
if we need to troubleshoot your installation,
so that we can help you more effectively.
If any of your packages are marked as "MISSING"
you will need to figure out what is wrong and possibly reinstall them.
Once all packages are marked as "OK"
we will ask you to submit this log file,
so that we can confirm that your installation was successful.
Details on where to submit will be provided later.

> Note that in general you should be careful running scripts unless they come from a trusted source as in this case (just like how you should be careful when downloading and installing programs on your computer).

## Attributions

* [Harvard CS109](http://cs109.github.io/2015/)
* [UBC STAT 545](http://stat545.com/packages01_system-prep.html#mac-os-system-prep) licensed under the [CC BY-NC 3.0](https://creativecommons.org/licenses/by-nc/3.0/legalcode).
* [Software Carpentry](https://software-carpentry.org/)
