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

### Starts Here

```elisp
;;; Please add the following code in you .emacs.d/init.el file
(require 'cl)
(when (>= emacs-major-version 24)
    (require 'package)
    (package-initialize)
    (add-to-list 'package-archives '("melpa" . "http://melpa.org/packages/") t)
    ;;(setq package-archives '(("gnu"   . "http://elpa.emacs-china.org/gnu/")
    ;;			      ("melpa" . "http://elpa.emacs-china.org/melpa/")))
    )



 ;; Add Packages
(defvar my/packages '(
                company
                hungry-delete
                swiper
                counsel
                smartparens
                js2-mode
                nodejs-repl
                exec-path-from-shell
		popwin
		reveal-in-osx-finder
		web-mode
		js2-refactor
		expand-region
		iedit
		org-pomodoro
		helm-ag
		flycheck
		auto-yasnippet
		monokai-theme
		evil
		evil-leader
		window-numbering
		evil-surround
		evil-nerd-commenter
		which-key
		powerline
		powerline-evil
		ivy
		smartparens
		pallet
		;; my own packages
		solarized-theme
		helm
		helm-gtags
		ggtags
		;;for python
		ein
		elpy
		py-autopep8
		websocket
		request
		dash
		s
		skewer-mode
		request-deferred
		smartrep
		org
		magit
		;;for latex
		auctex
		auctex-latexmk
		auctex-lua
		company-auctex
		cdlatex
		latex-preview-pane
               ) "Default packages")

(setq package-selected-packages my/packages)

(defun my/packages-installed-p ()
    (loop for pkg in my/packages
          when (not (package-installed-p pkg)) do (return nil)
          finally (return t)))

(unless (my/packages-installed-p)
    (message "%s" "Refreshing package database...")
    (package-refresh-contents)
    (dolist (pkg my/packages)
      (when (not (package-installed-p pkg))
        (package-install pkg))))
 ```
or start with a basic package installation script

```
;; Set up package.el to work with MELPA
(require 'cl)
(require 'package)
(add-to-list 'package-archives
             '("melpa" . "https://melpa.org/packages/"))
(package-initialize)
(package-refresh-contents)

(defvar my/packages '(
		evil
                company
                hungry-delete
                swiper
                counsel
                smartparens
                js2-mode))

(defun my/packages-installed-p ()
    (loop for pkg in my/packages
          when (not (package-installed-p pkg)) do (return nil)
          finally (return t)))

(unless (my/packages-installed-p)
    (message "%s" "Refreshing package database...")
    (package-refresh-contents)
    (dolist (pkg my/packages)
      (when (not (package-installed-p pkg)) ;; package-installed-p is a function to check if a package or newer version of a package is installed.
        (package-install pkg))))

;; Enable Evil
(require 'evil)
(evil-mode 1)
```
### Packages installed
Emacs packages:

0. Package 
Use-package

1. Programming related
1.0 general
Company: text completion; complete anything
Company-box
Ivy: another text completion from abo-abo
Auto-yasnippet
Flycheck
Fill-column-indicator
highlight-symbol
projectile

1.1 javascript and web
Js2-mode
Nodes-Real
Js2-refactor
skewer-mode
1.2 lisp
lispy
dash
s
1.3 python
ein
elpy
elpygen
py-autopep8
request-deferred
ob-ipython
indent-tools
pyimport

1.4 latex
auctex
auctex-latexmk
auctex-lua
company-auctex
cdlatex
latex-preview-pane
latex-pretty-symbols
latex-unicode-math-mode

1.5 org
Org
Org-pomodoro


2. Text editing
Hungry-delete: delete more space
Smartparens: automatically insert pairs
Expand-region: Expand region increases the selected region by semantic units
iedit: edit multple occurrences
Evil: vim simulator
Evil-leader: set leader key
Evil-surround:
Evil-nerd-commenter: 
Brow-kill-ring
multiple-cursors
smartrep
3. Text search
Swiper: 
Helm
Helm-ag
occur

4. Navigation
4.1 window navigate
Window-numbering
popwin
4.2 buffer navigate
4.3 text navigate
ggtags
Helm-gtags
avy
4.4 command navigate
Which-key

5. UI
Molokai-theme
solarized-theme
moe-theme
Doom-theme
Doom-modeline
Powerline
Powerline-evil
All-the-icons
All-the-icons-ivy
Dashboard
Beacon
Nyan-mode
neotree
Ivy-posframe
Awesome-tab

6. Utilizes
Exec-path-from-shell
Reveal-in-osx-finder
websocket
request
magit
ztree
### The basic organization of the emacs configuration folder
#### init.el
#### lisp folder
##### packages.el
##### ui.edl
##### custom.el
##### python.el

### Setup a pretty UI

### Great utilies


