# CLI Specification
This file defines the command line interface specification.
It includes the options and arguments it supports.
It also explains the usage of the rcnwc (recon-wc) program/tool.

## Terminology
**Option**

A flag or modifier beginning with '-' or '--'.

**Option Argument**

A value associated with an option.

**Operand**

A positional argument representing an input file.

## Options
` -c, --bytes`
         print the byte counts

` -m, --chars`
         print the character counts

` -l, --lines`
         print the newline counts

` --debug`
         indicate what line count acceleration is used

` --files0-from=F` or ` --files0-from F`
         read input from the files specified by
         NUL-terminated names in file F;
         If F is -, read names from standard input

` -L, --max-line-length`
         print the maximum display width

` -w, --words`
         print the word counts

` --total=WHEN` or ` --total WHEN`
         when to print a line with total counts;
         WHEN can be: auto, always, only, never

` --help`
         display this help and exit

` --version`
         output version information and exit
         
## Operands
` [FILE]...`
         0 or more input file paths

## Usage
```
rcnwc [OPTION]... [FILE]...
  or
rcnwc [OPTION]... --files0-from=F
```

## Rules

### Option Grouping
Option grouping in the sense of combining multiple *short* options
associated to a single hyphenated (`-`) option group  is supported.

#### Example
```bash
rcnwc -clw
```
prints bytes, newlines and word counts

### Option Parsing Termination
Option parsing termination using `--` is supported.
This feature is essential to avoid treating 
arguments that start with a hyphen
as options.

#### Example
```bash
rcnwc -- -file.txt
```
Stops parsing options once `--` is encountered, hence, avoiding
-file.txt being parsed as an option.


### Long Option Arguments
Long option arguments are supported in two formats.
1. Space separated
2. Equals-sign separated

#### Example
```bash
rcnwc --total=always
or
rcnwc --total always
```

## Summary

| Short | Long                | Argument     |
| :---: | :-----------------: | :----------: |
| `-c`  | `--bytes`           | No           |
| `-m`  | `--chars`           | No           |
| `-l`  | `--lines`           | No           |
| `-w`  | `--words`           | No           |
| `-L`  | `--max-line-length` | No           |
| —     | `--debug`           | No           |
| —     | `--files0-from`     | Yes (`F`)    |
| —     | `--total`           | Yes (`WHEN`) |
| —     | `--help`            | No           |
| —     | `--version`         | No           |

