# Emacs is a powerful platform for text object manipulation using Lisp programming

## What Emacs can do as an efficient text editor and IDE

* Text editing by VIM (yes, VIM as a text editor is very efficient)

* Text searching (grep)

* Find files in a project

* Code completion

* Code navigation

* Spell checking

* Syntax checking

* Debugging

* Find and replace cross several files

* File management

* Version control


# Here is the place to show the power of Emacs

Rule #1: Don't make Emacs too powerful at the begining. Don't drive an airplane when you can only drive a car.

Rule #2: Don't use start up kit unless you know everything there. You can easily get lost in the complicated settings and key bindings. 

The best way to use Emacs is to make it usable and build up its functions later.

## Emacs installation on MacOS

  brew tap d12frosted/emacs-plus
  
  brew install emacs-plus
  
## Learn a little bit Emacs-lisp

## Building emacs configuration file from scratch (not by yourself

  resources: 
  
  https://huytd.github.io/emacs-from-scratch.html
  
  the best:
  
  https://alhassy.github.io/init/
  
  absolutely new:
  
  https://medium.com/@suvratapte/configuring-emacs-from-scratch-intro-3157bed9d040
  
  advanced:
  
  https://justin.abrah.ms/dotfiles/emacs.html
  
  others:
  
  http://aaronbedra.com/emacs.d/
  
## Get familiar with well known emacs configurations and people

### Spacemacs
  
   Spacemacs incorparate lots of useful plugins and settings (almost every good plugins).
   
   https://github.com/syl20bnr/spacemacs
   
### Doom-emacs

  ready to use, out of box, Very fast, with spacemacs key bindings, nice UI
  
  https://github.com/hlissner/doom-emacs
  
### Centar emacs

  ready to use, out of box, nice UI
  
  https://github.com/seagle0128/.emacs.d
  
### M-emacs

  has everything you need, full features
  
  https://github.com/MatthewZMD/.emacs.d
  
### prelude

https://github.com/bbatsov/prelude
  
### purcell

https://github.com/purcell/emacs.d

### EgroEmacs

https://ergoemacs.github.io/

### Chen Bin

https://github.com/redguardtoo

### LazyCat

https://github.com/manateelazycat/lazycat-emacs

### Mike Zamansky

https://cestlaz.github.io/stories/emacs/

### General Emacs sites

https://emacs.zeef.com/ehartc

http://tuhdo.github.io/

## Build your own configuration file and setup your own workflow for using emacs

### People got scared away from Emacs because of the complex key bindings. But you really don't need to remember them. 

#### start everything by using M-x

     Inside Emacs, your input is your text. Emacs execute lots of functions to modify your text. Every modification on your text is realized by a function. Emacs has about 8000 functions to do text editing. We have to admit it is very powerful. The only shortcoming for Emacs is that it is too powerful. People get eaisly lost in all these functions.

#### query anything by M-x apropos

    This command will pop up an blank region for you to input your search item. It will return the related information.
    This is a must-have command for Emacs user.
    
#### Major mode and Minor mode

  The hundreds of functions bundled together based on the programming languages or tasks are collectively called Major mode;
  The functions bundled together based on more general editorial task like jumping around, searching, etc.
  
#### Help yourself using Ctrl + h

  You can image that it is hard to find the right functions to do the right thing. Using Ctrl + h to get the information about the functions, variables, documentations.
  
### Lisp programming (To learn Emacs, you need to learn Lisp language. But it is easy to learn)

https://github.com/caiorss/Emacs-Elisp-Programming/blob/master/Elisp_Programming.org

  


