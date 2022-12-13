# Contributing

## Bug report

For now [GitHub Bug Traker](https://github.com/zer0-x/moadaly/issues) is used for this project.

## Development

- The `stable` [Rust](https://www.rust-lang.org/) programming language is used mainly in this project.
- Dependencies managment and building is handled using [Cargo](https://doc.rust-lang.org/stable/cargo/).

### Style

- You should document every thing to keep the code easy for reading. Every file, every function and any line that need a comment.

To make every thing easy [**`pre-commit`**](https://pre-commit.com/) is used in this project, it should run in every commit, so you shouldn't commit any thing without checking it first.

#### Setup `pre-commit`
To make every thing easy [**`pre-commit`**](https://pre-commit.com/) is used in this project, it should run in every commit, so you shouldn't commit any thing without checking it.

First install it:
```shell
pip install pre-commit
```

> It's better to use you OS's package manager to install it.


Then add it as a git hook while you are inside the repository:
```shell
pre-commit install
```

### Documentation

Internal code should be documented with comments in it, while interfaces should be docuemented in separate files with respect to other developers who don't work in this project directly.

D-Bus interfaces should be written as an XML interface files that could be used in [`gdbus-codegen`](https://developer-old.gnome.org/gio/stable/gdbus-codegen.html) to generate a docbook that could be converted to a neat documentation.

<!-- TODO: -->
> TODO: Define tha work flow of generating the documentation from the interface files and what tool should be used to generate them.

The documentation should be uptodate in every release, any new interface or any modifecation in an old one should be documented before creating a new release to avoid confusion.
