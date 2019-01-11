
# Neovim ideas

This is a summary of my current issues with neovim and what would be the behavior of
the ideal solution. From this ideal solution description, I shall then work towards
the best way to achieve it, either by contributing to core neovim or by a plugin
or by forking neovim.

The end goal is to turn neovim into a modern IDE (like VSCode).

### Table of contents

 - [Auto-completion](#auto-completion)
 - [Search & replace](#search--replace)
 - [Git integration](#git-integration)
 - [Project management](#project-management)
 - [Fuzzy finder (for files & other)](#fuzzy-finder-for-files--other)
 - [Code exploration widgets (quick hover, peek definition, open documentation, etc)](#code-exploration-widgets-quick-hover-peek-definition-open-documentation-etc)
 - [Other widgets (file explorer, color picker, etc)](#other-widgets-file-explorer-color-picker-etc)
 - [Debbugging](#debbugging)


## Auto-completion

Neovim current auto-completion is by default bad (or very bad (or very very bad)).
To remediate this, we currently have various auto-completion plugins that compete
to provide a better experience.

  - [YouCompleteMe](https://github.com/Valloric/YouCompleteMe)
  - [deoplete](https://github.com/Shougo/deoplete.nvim)
  - [coc.nvim](https://github.com/neoclide/coc.nvim)

Both deoplete and coc.nvim allow other plugins to provide auto-completion sources.
It would be better if there was a consistent interface so the work is not repeated.

The ideal auto-completion needs:
 - Good typing experience: quick response, no freezing, no flickering,
   open as you type (YCM gets this behavior right). Keybinding triggered AC is archaic.
 - Intelligent suggestions: each file can get it's own sources, listed by relevance.
     Primary source would be coming from the LanguageServerProtocol client in use.

## Search & replace

**TODO**

## Git integration

**TODO**

## Project management

**TODO**

## Fuzzy finder (for files & other)

Current options:
 - CtrlP
 - fzf.vim

CtrlP has a nice feeling but is slow when searching large directories.
fzf.vim is fast with large directories but it has to start a process in a terminal,
so there is an unavoidable delay.
Both plugins have the issue that they mess the window layout, which doesn't feel nice.
They are also constrained by the window layout constraints.

Ideal solution:
 - Opens instantly
 - Supports asynchronous searching (e.g. for files), doesn't freeze like CtrlP
 - Exposes a consistent and feature-rich interface to be usable by any plugin.

## Code exploration widgets (quick hover, peek definition, open documentation, etc)

**TODO**

## Other widgets (file explorer, color picker, etc)

**TODO**

## Debbugging

**TODO**
