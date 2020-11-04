---
layout: page
title: Setting Up Visual Studio Code
---


### Overview

[Emacs](https://en.wikipedia.org/wiki/Emacs) is a family of text editors that are characterized by their extensibility.
It can be used as a simple editor, like Gedit, or as a full fledged IDE with all the bells and whistles. 
On this guide, when I talk about Emacs, I am refering to [GNU Emacs](https://www.gnu.org/software/emacs/).

If you are already using it, chances are that you already have your own custom configuration under the
[Emacs init file](https://www.gnu.org/software/emacs/manual/html_node/emacs/Init-File.html#Init-File).

If you don't have a custom configuration, or you are new, I recommend you to not waste your time
creating the ultimate configuration file and reuse one starter kit. Personally I like
[Spacemacs](https://www.spacemacs.org/), even when I do not use the evil mode very much, but
[Prelude](https://github.com/bbatsov/prelude), [Doom](https://github.com/hlissner/doom-emacs)
or [Purcel's config](https://github.com/purcell/emacs.d)
are good starting points


### Mandatory plugins

POP uses the [Black](https://black.readthedocs.io/en/stable/), [Prettier](https://prettier.io/) and
[EditorConfig](https://editorconfig.org/), so you should install and integrate them on your emacs configuration.

Therefore, I do recommend the following extensions:

* [python-black](https://github.com/wbolster/emacs-python-black)
* [PrettierJs for Emacs](https://github.com/prettier/prettier-emacs)
* [EditorConfig Emacs plugin](https://github.com/editorconfig/editorconfig-emacs)

All of them are accessible at [MELPA](https://melpa.org/#/).


### I am new to Emacs. A getting starting guide.

If you are new to Emacs, probably you will feel a bit confused at the beggining. I have never seen on any other place an "editor"
that can show you appointments, create todos, play tetris, connect to spotify, edit files and more. All of it without the use
of a mouse. So my first advice is to be practical. Don't do everything on Emacs just because you can. Take it easy.

Indeed I tend to use Emacs mostly to write, and to execute shell commands. So if you are new to Emacs I do
recommend the following:

* Start simple. Most of the defaults are good, and you can tweak them with some custom Lisp code. Try to start with little
things.
* Follow the Emacs tutorial. You can access it pressing <C-h t> (that means that you have to press the <Control> key and,
without releasing it, press the <h> key. Then release both the <Control> and the <h> keys and press the <t> key.
* I recommend you to see the [Emacs-rocks](http://emacsrocks.com/) videos.
* If you can, I do recommend a lot the book and the blog [Mastering Emacs](https://www.masteringemacs.org/)

Also, and this is just my opinion, I recommend to use a starter config. In my case I use [Spacemacs](https://www.spacemacs.org/)
because I really like the defaults and the layer separation even when I don't use the evil mode a lot.

To install it, you have to clone the Github repository onto ~/.emacs.d . After that, when you start Emacs again it will
load the started config. On the first prompt, you will be asked if you prefer to use the Evil Mode (in Emacs parlance that means
to mimic [Vim](https://www.vim.org/) to some extend), or do you prefer to continue using the controls of Emacs.

If for whatever reason you change your mind, you can change switch between the vilified and emacs modes
changing the dotspacemacs-editing-style variable on your ~/.spaceemacs file.

After that, it will prompt you for a which tool do you want to use to make completions. At the time of writing there is
support for [Helm](https://github.com/emacs-helm/helm) and [Ivy](https://github.com/abo-abo/swiper).

If you choose to use the vilified mode, and yet you don't know Vim well, you should follow the "Evil tutor start".
You can access it using the sequence <SPC h T>. Beware that most of the commands of the "Emacs mode" are not available
on the "Evil mode", so you cannot press <C-p> and go to the previous line.

Remember that "Evil mode" will mimic Vim, but only to some sort of degree.

### Common shortcuts

If you are in a hurry I share here the most common commands in Emacs mode:

* Movement:
  * <C-n> Next line 
  * <C-p> Previous line
  * <C-f> Following character
  * <C-b> Previous character
  * <C-l> Cycle between centering the cursor, set it at top or at bottom.
  * <C-v> Next page
  * <M-n> Next paragraph
  * <M-p> Previous paragraph
  * <M-f> Next word
  * <M-b> Previous word
  * <M-S-< > Beginning of the buffer
  * <M-S-> > End of the buffer
  * <C-a> Beginning of the line
  * <C-e> End of the line
* Internal
  * <C-x C-f> Find and open a file or a directory
  * <C-x b> Switch buffer
  * <C-x C-b> List buffers
  * <C-x C-s> Save buffer
  * <C-x C-c> Kill buffers and exit
  * <M-x> Execute an arbitrary Emacs function (not everything have a binding)
  * <C-SPC> Activate / Deactivate the mark
  * <C-g> Cancel
* Window management
  * <C-x 2> Split window below
  * <C-x 3> Split window right
  * <C-x o> Move to other window
  * <C-x 0> Delete current window
  * <C-x 1> Maximize current window
* Search
  * <C-s> Incremental search forward. You can place your search and press again <C-s> to go forward.
  * <C-r> Incremental search backward. You can place your search and press again <C-r> to go backward.
  * <M-s> Word search forward. You can place a sequence of words and they will be found
          regardless any type of punctuation.
  * <M-s _> Search for a symbol
  * <M-s .> Search for a symbol, but add the symbol where the caret is at the search.
  * <M-r> Word search backward.
  * <M-s M-w> Search the web for the text inside of the region
  * <C-M-s> Incremental regex search
  * <C-M-r> Reverse regex search

Don't worry if you forget some of them. No one will remember. But Emacs will help you to remember any of them. For
examplo, if you want to switch a buffer, and you only remember that it starts with <C-x>, after pressing that, a
popup will appear showing what can you do next.

And, if you need help with a function, a variable, or whatever, press <C-h>. Emacs keeps track of everything, so,
it is the best documentation available.

Also, keep in mind that Spacemacs will create a bunch of new bindings, most of them available under the
<M-m> prefix on a Emacs mode or under a <SPC> prefix in a vilified mode. Spacemacs bindings tend to be
easier to remember so I do recommend to look at them.


### A guide to configure the mandatory extensions on Spacemacs

All your configuration of Spacemacs lives inside a file in ~/.spacemacs . There are different sections that I am going to
show and that you must be aware of.

First of all. Don't worry about the parenthesis. If you are new probably you will be wondering why are parenthesis everywhere.
Emacs has been written in a language called Emacs Lisp, and, as all LISP variants, this is its syntax. I do not have the
time nor the space here to discuss it, but basically, when you configure you Emacs, you write LISP code. That's all.

At the very beginning of the ~/.spacemacs file you will find a function declaration, called
dotspacemacs/layers. This is a very important want as it will define how the different layers will work. If you scroll down
a bit, you will find a variable called "dotspacemacs-configuration-layers". That variable is defined as a list of
elements, and each element will enable a layer. You can access a list of layers [here](https://www.spacemacs.org/layers/LAYERS.html),
but I recommend to add the following ones:

* html
* markdown
* yaml
* javascript
* python
* auto-completion
* better-defaults
* git
* syntax-checking


I do not use any special configuration on any of those layers at the moment of writing.

After that, you will find a variable called "dotspacemacs-additional-packages". I do recommend to add the
extra packages that I mentioned earlier. So the list will become like this

```lisp
'(rjsx-mode
  python-black
  editorconfig
  prettier)
```

Please, don't use "," to separate elements on a list. Use spaces, tabs or newlines instead. I also added rjsx-mode to
have support for react JSX syntax.

If you scroll down a bit more, you will find another function definition called "dotspacemacs/init". Here, general config
related to spacemacs lives. As it is very well documented, I recommend you to read it and make changes where you
think it is appropriate. My personal chooses are:

* I add (agenda . 3) and (todos . 3) to show on the startup my TODOs and my agenda.
* Usually, I always increase the font on dotspacemacs-default-font
* I really like fuzzy search, so I set the dotspacemacs-helm-use-fuzzy to 'always
* I set dotspacemacs-enable-paste-transient-state to true, so yanking will cycle the kill ring.
* I tend to use Emacs on full-screen mode, so I set dotspacemacs-full-screen-at-startup to true.
* If you use the vilified mode, I recommend to set dotspacemacs-fullscreen-at-startup to 'relative,
  otherwise, set it to true
* I changed dotspacemacs-smart-closing-parenthesis to true
* I want to not have trailing spaces on my code, but usually it is rude to change code that
  has been write for someone else. Also, it is not a good idea to have thousand of changed lines
  for a small PR. So, I set the dotspacemacs-whitespace-cleanup to 'changed. That way it will
  remove any trailing spaces when you save the buffer, but only on those lines that you touched.


After that function, scrolling a little bit down, you will find another function called
dotspacemacs/user-init. This function is called before the call to any layer, so the code lying here should
not be dependable. Here is the configuration that I am using at the time of writing this (I added comments to explain
everything):

```lisp
(defun dotspacemacs/user-init ()
  "Initialization function for user code.
It is called immediately after `dotspacemacs/init', before layer configuration
executes.
 This function is mostly useful for variables that need to be set
before packages are loaded. If you are unsure, you should try in setting them in
`dotspacemacs/user-config' first."

  ;; I want to start Emacs at ~/Code, because there is where my code lives.
  (getenv "HOME")
  (setq-default

   default-directory "~/Code"

   ;; Use ASCII art to show the folders on the nerdtree
   neo-theme 'ascii

   ;; Disable lockfiles
   create-lockfiles nil

   ;; This line ensures that dired sorts directories first
   insert-directory-program "gls" dired-use-ls-dired t

   ;; As I use Emacs on a fullscreen mode, I want to see a time on the
   ;; status bar in order to keep track of the time
   display-time-24hr-format t
   display-time-day-and-date t
   display-time-format "%d %b %Y %H:%M"

   ;; If you are using Mac os, consider to add the following two lines
   ;; They will rebind the Command key to meta and the
   ;; Option key will be unused.
   ;; I found that, default configuration of spacemacs it is a bit annoying
   ;; as it does just the opposite, making difficult to write characters
   ;; like € or #
   mac-command-modifier 'meta
   mac-option-modifier 'none

   ;; Don't ask for confirmation when I delete or copy a whole directory
   ;; tree on dired (caution)
   dired-recursive-deletes 'always
   dired-recusive-copies 'always

   ;; Indent JS with 2 spaces. Also ensure that switch cases are indented.
   js2-basic-offset 2
   js-indent-level 2
   js-switch-indent-offset 0

   ;; Indent typescript with 2 spaces. I do not add anything to the switch case
   ;; because by default it is true
   typescript-indent-level 2

   ;; Indent CSS and HTML with two spaces
   css-indent-offset 2
   web-mode-markup-indent-offset 2
   web-mode-css-indent-offset 2
   web-mode-code-indent-offset 2
   web-mode-attr-indent-offset 2)

   ;; If you uncomment the following line, <C-c> and <C-v> will be Copy & Paste.
   ;;;(cua-mode t)

  ;; Ensure the time is show on the status bar
  (display-time-mode 1))
```

Finally, if you continue to scroll down a bit more, you will find a function called
"dotspacemacs/user-config". This function is executed at the end of spaceemacs initialization
and can be used to add minor modes or change the spacemacs defaults.

The first thing that I am going to do is to replace JS mode to RJSX mode, as we are using
React and we want support for JSX features. After that, I would like to have the minor mode
python-black-on-save-mode active when I am editing any python file and the prettier-js-mode when
I am editing any JavaScript file.

To do it, this is the needed code:

```lisp
(defun dotspacemacs/user-config ()
  "Configuration function for user code.
This function is called at the very end of Spacemacs initialization after
layers configuration.
This is the place where most of your configurations should be done. Unless it is
explicitly specified that a variable should be set before a package is loaded,
you should place your code here."
  (add-to-list 'auto-mode-alist '("\\.jsx?$" . rjsx-mode))
  (add-hook 'python-mode-hook 'python-black-on-save-mode)
  (add-hook 'rjsx-mode-hook 'prettier-js-mode))
```

That's all. Obviously there is a lot more, but most of it is covered by the Spacemacs config and I am happy
with the defaults.
