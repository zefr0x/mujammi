> **Note** : This project is still in the planning stage.

<div align = center>

<h1>Mujammi' | مُجَمِّع</h1>

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/zer0-x/mujammi/main.svg)](https://results.pre-commit.ci/latest/github/zer0-x/mujammi/main)

A game changing, feature-rich, efficient, blazingly fast, highly extendable and easily integrated **news aggregation backend** that aims to make the process more organized, light-weight, secure and private.

It's **not** an RSS aggregator nor a feed reader, it's a `feed aggregator` which act as a middle man by accessing feeds using `informants`, and communicating with `feed reeders` using [`D-Bus`](https://en.wikipedia.org/wiki/D-Bus) and [`Named Pipes`](https://en.wikipedia.org/wiki/Named_pipe). It takes control of the database and it organizes everything so much that the feed reader's only job is to display the news.

---

[<kbd><br><b>Install</b><br><br></kbd>](#installation)
[<kbd><br><b>Contribute</b><br><br></kbd>](CONTRIBUTING.md)
[<kbd><br><b>Packaging</b><br><br></kbd>](PACKAGING.md)
[<kbd><br><b>Q&A</b><br><br></kbd>](#qa)

---

<br>

</div>

## Features
- 🧾 Free software under the [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html) licence.
- 💪 Written in the [Rust](https://www.rust-lang.org/) programming language.
- ...

## Concepts and Ideas
1. `Informant`: The part that fetch feeds from there sources and convert them to a generic format that could be stored in the database.
    - They could be `Builtins` or `Extensions`.
    - Each one is responsable for dealing with specific protocol or type of feeds.
2. ...

## Installation
### AUR
Not available yet...
### From the git repo <sup>`(Not recomended)`</sup>
1. Clone the repo from github
```shell
git clone https://github.com/zer0-x/mujammi.git
```
2. Use `cargo` to install it
```shell
cargo install --path=./mujammi
```

## Troubleshooting

## Q&A

Q: What does `Mujammi'` mean?
- It is an Arabic word `مُجَمِّع` that could be translated to `aggregator` in english.
