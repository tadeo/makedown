# [makedown](https://github.com/tzador/makedown) A Markdown powered Makefile alternative

`makedown` (aka Makefile + Markdown) is motivated by developers need to define
multiple scripts in one file next to their documentation, and have a handy way to
trigger them from terminal.

`Makefile`s are great for this, but are lucking some of the [`makedown`](https://github.com/tzador/makedown) features,
such as syntax highlighting, hierarchical scanning and embedded documentation.

There are also `package.json` scripts in `node.js` world, but users are forced to write script commands in one line.

It is implemented in Python for portability reasons, since most Unix-like systems
already have a Python interpreter installed.

## Key Features

- [x] **Executable Markdown Scripting**: Use markdown files (.md) to organize commands and their documentation.
- [x] **Multilingual Execution**: Supports `zsh`, `bash`, `javascript`, `python` and **infinitely** many more.
- [x] **Syntax Highlighting**: Leverages markdown code blocks for readability.
- [x] **Flexible Code Blocks**: Support for triple backtick code blocks.
- [ ] **Autocomplete Support**: ZSH completions for a smoother workflow.

## How to use

### Install

```bash
pip install makedown
```

### Define commands in a markdown file

````markdown
# my_scripts.md

Here are a few examples of commands:

## [hello]() Prints a welcome message

```bash
echo "hello, world!"
```
````

### Executing commands

To run commands in a markdown file, execute `makedown` from the same directory or any subdirectory:

```bash
makedown hello
```

A shorter version is also available:

```bash
m hello
```

### Printing help

To see all the available commands with their documentation, use one of the following:

```bash
makedown --help
```

or just run it without any arguments:

```bash
makedown # just `m` also works
```

### Using other languages

```python
print("hello, world!")
```

### Upgrade

```bash
pip install --upgrade makedown
```

### Uninstall

```bash
pip uninstall makedown
```

## Development

These are actual `makedown` commands:

### [venv]() Create a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate && pip install --upgrade pip
```

### Activate the virtual environment manually everytime you start a new shell

```bash
source venv/bin/activate
```

### [install]() Install Python dependencies

```bash
pip install setuptools wheel twine black
```

### [format]() Format the source code

```bash
black makedown.py
```

### [build]() Build the package

```bash
rm -rf build dist makedown.egg-info
python setup.py sdist bdist_wheel
```

### [publish]() Publish the package to PyPI

```bash
makedown build
twine upload dist/*
```
