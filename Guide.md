# Computerome user guide

Here we will go through some sections of the original [Computerome's Wiki](https://www.computerome.dk/).

## 1. Getting started

### 1.1. Login and access

First of all, to inquire about access, please contact DTU National Lifescience Center, on E-mail: *HPC@bio.dtu.dk.*

Once your account has been created, you will be provided with your personal login **password** and a **PASSCODE**, which can be received on the mobile phone and/or Google Authenticator. Contact also *HPC@bio.dtu.dk.* to be able to obtain the PASSCODE from Google Authenticator.

In the terminal, you should write the following command in order to login with your user account and hereafter you will be asked for the mentioned password and PASSCODE. :

```
username@computerome.cbs.dtu.dk
```

*Windows PC users* are are recommended to use the free Windows SSH client PuTTY for command-line SSH login to Computerome.

### 1.2. Setting up the login node

Sometimes it may be convinient to create shortcuts for some (long) commands which we use very frequently, in this way by typing fewer characters we would get the same result. This is called creating an *Alias*.

Moreover, it may also be interesting to automate the loading of those *modules* which are oftenly required by the user. For example, those involved in jobs submission *(Further details in section 1.3. Running/Submitting jobs)*. 

The personal *home directory*, can also be changed to any desired directory where the user has permitted access. The default assigned home directory can be seen by typing in the terminal:

```
cd
pwd

```

In order to create these *Alias*, automatically load these modules in every session login and change the home directory, the *.bashrc* file has to be modified. *Alias* have to be defined and the command for loading a certain module has to be written in the *.bashrc* file.
This can be done with any terminal-text editor, the next example uses *nano*:

```
# Go to home directory
cd
nano .bashrc
```

After this, .bashrc file opens and contains, for example:

```
# .bashrc

# Source global definitions
if [ -f /etc/bashrc ]; then
        . /etc/bashrc
fi

# Uncomment the following line if you don't like systemctl's auto-paging feature:
# export SYSTEMD_PAGER=


# User specific aliases and functions
module load gcc

```

Once the file is open, under *"# User specific aliases and functions"* we can add for example:

**Alias** - Create an alias for the current directory's content visualization command, as a list, sorted by  time modification and showing the size of the files/directories ```ls -lth```. It is important not to leave spaces between the characters defining the alias *(alias_name=command)*: 

```
alias le='ls -lth'

```
**Module loads** - As before, write in a new line the command for loading a given module, for example, those involved in jobs submission:

```
module load moab torque
module load xqsub/1.0

```
**Setting new home directory** - Write in a new line ```cd ```, space and the path of the desired new home directory:


### 1.3. Running/Submitting jobs
In general, keep in mind jobs **should not be run on the login node** – it is only used as a platform to **submit jobs** into the high-performance cluster.

Then, *how to submit jobs from the login node?*






