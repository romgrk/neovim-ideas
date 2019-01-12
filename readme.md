
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
 - [Task runner](#task-runner)
 - [Ctags](#ctags)
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
 - Inline reference to the documentation of a function (Eclipse like)
 - Arguments hinting after auto-completing a function

## Search & replace

These are the use-cases that need to be covered:
 - Search for a pattern in the current project files
 - Replace that pattern
 - Options: plain, regex, case-sensitive
 - Quickly specify pattern of files to match

## Git integration

**TODO**

## Project management

**TODO**

## Task runner

Current task running plugins usually suffer from a lack of visual interface.

## Ctags

Haven't found a decent ctags plugin yet.
Requirements:
 - It works
 - Can be customized by project (file patterns to match/ or exclude)

## Fuzzy finder (for files & other)

Current options:
 - CtrlP
 - fzf.vim
 - Denite

CtrlP has a nice feeling but is slow when searching large directories.
fzf.vim is fast with large directories but it has to start a process in a terminal,
so there is an unavoidable delay.
Both plugins have the issue that they mess the window layout, which doesn't
feel nice (screen flickers).

Ideal solution:
 - Opens instantly
 - Supports asynchronous searching (e.g. for files), doesn't freeze like CtrlP
 - Exposes a consistent and feature-rich interface to be usable by any plugin.
 - Smart matching algorithm. Default one should be made for filename matching
   (fzy algorithm seems decent)

Other use-cases: jump to symbols

## Code exploration widgets (quick hover, peek definition, open documentation, etc)

Quick hover: should be provided by the editor to any plugin that can handle it.

## Other widgets (file explorer, color picker, etc)

**TODO**

## Debbugging

**TODO**
