
# Neovim ideas

This is a summary of my current issues with neovim and what would be the behavior of
the ideal solution. From this ideal solution description, I shall then work towards
the best way to achieve it, either by contributing to core neovim or by a plugin
or by forking neovim.

The end goal is to turn neovim into a modern IDE (like VSCode).


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

## Other widgets (file explorer, color picker, etc)

**TODO**

## Debbugging

**TODO**
