# dupeGuru

[dupeGuru][dupeguru] is a cross-platform (Linux, OS X, Windows) GUI tool to find duplicate files in
a system. It's written mostly in Python 3 and has the peculiarity of using
[multiple GUI toolkits][cross-toolkit], all using the same core Python code. On OS X, the UI layer
is written in Objective-C and uses Cocoa. On Linux, it's written in Python and uses Qt5.

The Cocoa UI of dupeGuru is hosted in a separate repo: https://github.com/hsoft/dupeguru-cocoa

## Current status: Unmaintained

I haven't worked on dupeGuru for a while and frankly, I don't want to. I never had any duplicate
problems so I don't even care about the *raison d'être* of this thing.

I don't want to answer incoming issues and I don't want to let them pile off unanswered either,
that feels rude. So here I am, being straightforward about it.

If you're considering using dupeGuru, you might want to give it a try but if it doesn't meet your
needs I suggest that you use another program because it's unlikely to ever be improved again.

If you're a developer wanting to pick it up, by all means, do so! Fork it off and release
something. I will be more than happy to "officially" point to any fork that remotely looks like a
serious effort. I will also be happy to assist if you have questions about the code.

Good bye dupeGuru,
Virgil Dupras

## Contents of this folder

This folder contains the source for dupeGuru. Its documentation is in `help`, but is also
[available online][documentation] in its built form. Here's how this source tree is organised:

* core: Contains the core logic code for dupeGuru. It's Python code.
* qt: UI code for the Qt toolkit. It's written in Python and uses PyQt.
* images: Images used by the different UI codebases.
* pkg: Skeleton files required to create different packages
* help: Help document, written for Sphinx.
* locale: .po files for localisation.

There are also other sub-folder that comes from external repositories and are part of this repo as
git submodules:

* hscommon: A collection of helpers used across HS applications.
* qtlib: A collection of helpers used across Qt UI codebases of HS applications.

## How to build dupeGuru from source

### Windows
For windows instructions see the [Windows Instructions](Windows.md).

### Prerequisites

* [Python 3.4+][python]
* PyQt5

### make

dupeGuru is built with "make":

    $ make
    $ make run

### Generate Ubuntu packages

    $ bash -c "pyvenv --system-site-packages env && source env/bin/activate && pip install -r requirements.txt && python3 build.py --clean && python3 package.py"

### Running tests

The complete test suite is run with [Tox 1.7+][tox]. If you have it installed system-wide, you
don't even need to set up a virtualenv. Just `cd` into the root project folder and run `tox`.

If you don't have Tox system-wide, install it in your virtualenv with `pip install tox` and then
run `tox`.

You can also run automated tests without Tox. Extra requirements for running tests are in
`requirements-extra.txt`. So, you can do `pip install -r requirements-extra.txt` inside your
virtualenv and then `py.test core hscommon`

[dupeguru]: https://www.hardcoded.net/dupeguru/
[cross-toolkit]: http://www.hardcoded.net/articles/cross-toolkit-software
[documentation]: http://www.hardcoded.net/dupeguru/help/en/
[python]: http://www.python.org/
[pyqt]: http://www.riverbankcomputing.com
[tox]: https://tox.readthedocs.org/en/latest/
