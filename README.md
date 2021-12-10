# PvP - The Ultimate Python Virtualenv and Package Manager

*Python package manager to end all Python package managers*

Python virtualenv and Pip (PvP) manager is a modern,
standards-compliant, fast, beautiful package manager created
with love.

Also, it's a very small shell script.

What's not to like?

## Installation

Get it directly from the source:

    git clone git@github.com:senko/pvp.git
    cd pvp/

Copy the script somewhere in your `$PATH`.

If you're on a modern Linux distribution:

    cp pvp ~/.local/bin
    chmod a+rx ~/.local/bin/pvp

or to install for all users (should work on both Linux and MacOS):

    sudo cp pvp /usr/local/bin/
    sudo chmod a+rx /usr/local/bin/pvp

Add the contents of `pvp-bashrc` to your shell startup script
(most likely `~/.bashrc` unless you're one of the cool kids and
use Zsh, in which case it's probably `.zshrc`).

Re-enter the shell or source your shell startup script and you're
ready to go!

## Usage

Initialize a Python virtual environment in the current directory:

    pvp init

Install packages:

    pvp add pkgname otherpkgname

Remove packages:

    pvp rm pkgname

See the list of installed packages:

    pvp list

Activate a Python virtual environment that's been initialized in
the current directory or any of its ancestors:

    pvp

Deactivate a Python virtual environment, if it's activated:

    deactivate

Run Python within virtual environment without activating it for the current
shell:

    pvp run manage.py runserver

## How it works

[Magic!](https://xkcd.com/353/)

Oh, how it *actually* works?

It uses the awesome `pip` and `venv` modules from Python 3 standard library
and a little bit of shell scripting to make using them easier.

PvP will figure out the virtual environment you're in based on your current
directory. It searches for `.venv` sub-directory in the current directory,
then the parent directory, then its parent, all up to `/`.

The first `.venv` directory that is found will be used. If none are found,
PvP assumes it's not running in a project that has a virtual environment
set up.

This is similar what `npm` does when searching for `node_modules`.

Curious minds are invited to check the source. It's a pretty short read.

## Contributing

If you've found a bug, problem, security issue, have an idea, suggestion,
comment, or just want to rewrite it in Rust for speed and memory safety,
I've just got two rules:

1. Bug reports and patches are more than welcome
2. I don't guarantee I'll fix anything or merge any patches you send

## But it doesn't do X!

Listen, I understand. I really do. Have you tried using
[pipenv](https://github.com/pypa/pipenv),
[Poetry](https://python-poetry.org/),
[conda]https://anaconda.org/anaconda/python,
[PDM](https://pdm.fming.dev/),
[homebrew](https://docs.brew.sh/Homebrew-and-Python#python-3x),
[apt](https://packages.ubuntu.com/search?keywords=python&searchon=names&suite=impish&section=all),
[rpm],
or writing your own?

It's really a rite-of-passage for every serious Python
developer, you know.

## License

[MIT](LICENSE.txt). Gee, I do hope Amazon doesn't fork this and make an
AWS product out of it.

## Is this a joke?

Obviously. I use it every day.
