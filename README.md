# lg - grep me from a line!

Passes a string given in argument to grep

## Why would I use lg?

You probably arleady wanted to grep from a line using :

```bash
echo "$yourvar" | grep "your regexp"
```

Using lg, it is much simpler and cleaner :

```bash
lg "$yourvar" "your regexp"
```
You may also wanna pass arguments to grep :

```bash
  lg "$yourvar" "your regexp" arg1 arg2 argX
```

=> Give as much args as you want and the way you want, just put them *after* `STRING` and `REGEXP` arguments.

## Installation

### Requirements

You need the fish shell interpreter to execute this script:

* Ubuntu and Debian based: `sudo apt update && sudo apt install fish`
* Archlinux: `sudo pacman -Syu && sudo pacman -S fish`
* Fedora: `sudo dnf install fish`
* MacOS (brew): `brew install fish`

`grep` is also needed but it's usually pre-installed on \*nix systems.

### Install lg

```bash
sudo wget https://raw.githubusercontent.com/lapingenieur/lg/lg -O /usr/local/bin/lg -nv
sudo chmod a+x /usr/local/bin/lg
```

### Add fish-shell autocompletion

*(only works when using `lg` from within the fish shell interpreter)*

```bash
wget https://raw.githubusercontent.com/lapingenieur/lg/lg-completion.fish -O ~/.config/fish/lg-completion.fish
echo "source ~/.config/fish/lg-completion.fish"
```

## Usage

```bash
lg STRING REGEXP ARG...
```
## Arguments

  | Argument | Description |
  |----------|-------------|
  | `STRING` | a string to give to grep |
  | `REGEXP` | what to grep, often a regexp |
  | `ARG`    | arguments given directly to grep |

> Note: lg needs at least 2 arguments (`STRING` and `REGEXP`) to work, unsless you'll see a help message.

## Example usage

```bash
lg "Hi there!" "th.r.*!$"
lg "333@dew.sw" "\.[^\.]+$" -oE     # only output .sw
lg "rerere.ere" "\.e" -q            # no output : -q means silent
lg "HelLO::wOrLD" "hello" -i        # case insensitive
```

For more infos look at grep's manual page : `man grep`

---

> original distribution written in fish-shell script
> written by lapingenieur
> source code: https://github.com/lapingenieur/lg
> contact: lapingenieur@gmail.com'
