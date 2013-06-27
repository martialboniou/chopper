chopper
=======

Interactive binary search for a line within a window or a buffer

Setup:
------

Put `chopper.el' where you keep your elisp files and add something like the following to your .emacs file:

###Simpler way:

       (require 'chopper)
       (eval-after-load "chopper"
         '(progn
           (global-set-key [(meta up)] 'chopper-window-move-up)
           (global-set-key [(meta down)] 'chopper-window-move-down)
           (global-set-key [(shift meta up)] 'chopper-buffer-move-up)
           (global-set-key [(shift meta down)] 'chopper-buffer-move-down)))

###Better way:

       (autoload 'chopper-window-move-up "chopper" "Move up half the remaining distance of previous chop move.")
       (autoload 'chopper-window-move-down "chopper" "Move down half the remaining distance of previous chop move.")
       (autoload 'chopper-buffer-move-up "chopper" "Move up half the remaining distance of previous chop move in the whole buffer.")
       (autoload 'chopper-buffer-move-down "chopper" "Move down half the remaining distance of previous chop move in the whole buffer.")
       (global-set-key [(meta up)] 'chopper-window-move-up)
       (global-set-key [(meta down)] 'chopper-window-move-down)
       (global-set-key [(shift meta up)] 'chopper-buffer-move-up)
       (global-set-key [(shift meta down)] 'chopper-buffer-move-down)

###Best way:

Using el-get following recipe:
      https://raw.github.com/martialboniou/Dots/recipes/.emacs.d/data/Recipes/chopper.rcp

Note:
-----

As this script use `last-command`, you should use a keybinding in order to use this four interactive functions.
