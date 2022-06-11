<p align="center">
  <img alt="header image" src="https://raw.githubusercontent.com/caarlos0/dotfiles.fish/master/docs/header.svg" height="350" />
  <h2 align="center">carlos' dotfiles</h2>
  <p align="center">Config files for Fish, Go, Editors, Terminals and more.</p>
</p>

---

Forked from my [ZSH dotfiles](https://github.com/caarlos0/dotfiles), those are
my Fish Shell config files, together with editor, macOS configs and other
goodies.

The main reasons for the fork are:

- a lot of things I have out of the box on Fish needed plugins on zsh
- Fish autocompletion is awesome
- Fish syntax is easier to use
- Fish is more modern.

This is an attempt to make the same things I had on my ZSH dotfiles on Fish.
For the user, it should look pretty much the same, although under the hood
there are a lot of changes.

Config files are still topical, and even though aliases are not a thing on Fish,
files are named like that still (and hold both functions and abbreviations).

The auto-update feature was removed, as it was hacky on ZSH and I didn't want to
do it. Instead, now the bootstrap script is better and can be run multiple times
without any issues, so, to update, `git pull` and run the `bootstrap.fish`
script.

## Installation

### Dependencies

First, make sure you have all those things installed:

- `git`: to clone the repo
- `curl`: to download some stuff
- `tar`: to extract downloaded stuff
- `fish`: the shell
- `sudo`: some configs may need that

### Install

Then, run these steps:

```console
$ git clone https://github.com/caarlos0/dotfiles.fish.git ~/.dotfiles
$ cd ~/.dotfiles
$ ./script/bootstrap.fish
```

> All changed files will be backed up with a `.backup` suffix.

#### Update

To update, you just need to `git pull` and run the bootstrap script again:

```console
$ cd ~/.dotfiles
$ git pull origin master
$ ./script/bootstrap.fish
```

## Revert

Reverting is not totally automated, but it pretty much consists in removing
the fish config and dotfiles folder, as well as moving back some config files.

**Remove the folders:**

```console
$ rm -rf ~/.dotfiles ~/.config/fish
```

**Some config files were changed, you can find them using `fd`:**

```console
$ fd -e backup -e local -H -E Library -d 3 .
```

And then manually inspect/revert them.

## Recommended Software

- [`alacritty`](https://github.com/alacritty/alacritty) a cross-platform, OpenGL terminal emulator;
- [`delta`](https://github.com/dandavison/delta) for better git diffs;
- [`fd`](https://github.com/sharkdp/fd) a simple, fast and user-friendly alternative to `find`;
- [`fzf`](https://github.com/junegunn/fzf) for a fuzzy-finder;
- [`gh`](https://github.com/cli/cli) for more GitHub integration with the terminal;
- [`grc`](https://github.com/garabik/grc) to colorize command's outputs;
- [`starship.rs`](https://starship.rs) the shell we are using;
- [`kubectx`](https://github.com/ahmetb/kubectx) for better Kubernetes context and namespace switch;

To install them all with `brew`:

```console
$ brew install fish git-delta fzf gh grc kubectx starship zoxide fd exa alacritty
```

On Ubuntu:

```console
sh -c "$(curl -fsSL https://starship.rs/install.sh)"
sudo apt install fish grc fzf zoxide fd-find exa alacritty
```

## macOS defaults

You use it by running:

```console
~/.dotfiles/macos/set-defaults.sh
```

And logging out and in again or restart.

## Themes and fonts being used

Gruvbox (dark - high contrast) and MonoLisa Nerd Font.

## Screenshots

<img width="3008" alt="image" src="https://user-images.githubusercontent.com/245435/173171807-89d86eee-6e2b-4fad-9197-0ce6aeb77f78.png">

<img width="3008" alt="image" src="https://user-images.githubusercontent.com/245435/173171829-8749e953-72fb-497c-b09f-e9b89ef4feca.png">

