# Grep

A utility for grepping that isn't limited to a specific program

## Fallbacks
`grep.vim` will try to use `git-grep` if available.
If not, it will fallback to `ag`.
If `ag` isn't installed, it will prompt the user to install one of the two

## Installation
### Ag

You have to install [ag](https://github.com/ggreer/the_silver_searcher), of course.

Install with Homebrew:

```bash
brew install the_silver_searcher
```

Add this to your `~/.vimrc`:
```bash
let g:grepprg="ag --nogroup --column"
```

### Ack
You have to install [ack](http://beyondgrep.com/), of course.

Install with Homebrew:

```bash
brew install ack
```

Add this to your `~/.vimrc`:

```bash
let g:grepprg="ack -H --nocolor --nogroup --column"
```

### Git grep
Install git, which you probably have installed
Do nothing, git grep is the default grep command

## Usage
`:Grep [options] {pattern} [{directory}]`

Search recursively in {directory} (which defaults to the current directory) for the {pattern}.

Files containing the search term will be listed in the split window, along with
the line number of the occurrence, once for each occurrence.  [Enter] on a line
in this window will open the file, and place the cursor on the matching line.

Just like where you use :grep, :grepadd, :lgrep, and :lgrepadd, you can use `:Grep`, `:GrepAdd`, `:LGrep`, and `:LGrepAdd` respectively. (See `doc/grep.txt`, or `:h Grep` for more information.) 

This plugin is almost copy and pasted from [mileszs' ack.vim plugin](https://github.com/mileszs/ack.vim).
