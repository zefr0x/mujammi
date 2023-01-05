> **Note** : This project is still in the planning stage.

<div align = center>

<h1>Mujammi' | مُجَمِّع</h1>

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/zer0-x/mujammi/main.svg)](https://results.pre-commit.ci/latest/github/zer0-x/mujammi/main)

A game changing, feature-rich, efficient, blazingly fast, highly extendable and easily integrated **news aggregation [deamon](<https://en.wikipedia.org/wiki/Daemon_(computing)>)** that aims to make the process of aggregating news more organized, light-weight, secure and private.

It's **not** just an RSS aggregator nor a feed reader, it's a `feed aggregator` which act as a middle man by accessing feeds from any source using `informants`, and communicating with `feed reeders` using [`D-Bus`](https://en.wikipedia.org/wiki/D-Bus) and [`Named Pipes`](https://en.wikipedia.org/wiki/Named_pipe) to display the news. It takes control of the database and it organizes everything so much that the feed reader's only job is to display the news.

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

## Concepts, Definitions and Ideas

1. `Informant`: The part that fetch feeds from there sources and convert them to a generic format that could be stored in the database.
   - They could be `Builtins` or `Extensions`.
   - Each one is responsable for dealing with specific protocol or type of feeds.
2. `Feed Aggregator`: It's what `Mujammi` is. It access feeds using `Informats`, store them in a database, and provides an [API](https://en.wikipedia.org/wiki/API) for `Feed Readers` to communicate with it and get contents.
   - It's the core of the oporation and we can have only one of it.
   - It should run all the time in the background.
   - For simple communication with `Feed Reader` it uses [`D-Bus`](https://en.wikipedia.org/wiki/D-Bus).
   - When we have a lot of data it will send them using [`Named Pipes`](https://en.wikipedia.org/wiki/Named_pipe) to `Feed Reader`.
   - The `D-Bus`/`Named Pipes` communication interface should be good for most use cases, but if not, it is moduler, so you can create another one rather then using it.
   - It is not usual for the user to interact with it directly.
   - It's not ment to be used for huge amount of users as a web service for example.
   - It can sync data between multiple devices using a special syncing protocol and service that could be self-hosted.
   - It should support every feature a feed aggregator should have.
   - ...
3. `Feed Reader`: An application that display feeds and there contents to the user, by communicating with the `Feed Aggregator`.
   - They might also provide an interface to configure the `Feed Aggregator` and to manage feeds and everything related to them that the user might want to change. But no problem if this was a separate thing.
   - They are separate projects that just use the `Feed Aggregator`'s [API](https://en.wikipedia.org/wiki/API), there developers are able to build them as they like and users might select any one to use based on what they prefer.
   - It should not be running in the background.
   - It should not access the network by it self. It can only request the `Feed Agregator` for some extra media for a specific news or feed. The `Feed Aggregator` will take care of creating a secure and private request to obtain the extra media.
4. A notification/status interface might be implemented as part of the `Feed Reader` or as a completly separate project.
   - It might be an icon in the system tray or a desktop wedget or a script that output some text to be displayed somewhare.
   - It should wait for a signal from the `Feed Aggregator` to update it's information.
   - It ment to help saving time and resources by giving the user the summary so he don't need to open the whole `Feed Reader`.
5. ...

## Installation

### AUR

Not available yet...

### From the git repository

> You need to have [`cargo`](https://doc.rust-lang.org/cargo/) installed in you system.

1. Clone the repository from github

```
git clone https://github.com/zer0-x/mujammi.git
```

2. Go to the directory

```
cd mujammi
```

3. Checkout to a release tag e.g. v1.0.0

```
git checkout vx.x.x
```

4. Use `cargo` to install it

```shell
cargo install --path=.
```

## Q&A

Q: Why?

- To improve the overall RSS clients experience and news aggregators in general on the Linux Desktop, since the existing clients usually use a lot of resources, don't support every feature a feed aggregator should have, and a lot of other disadvantages. Having a bad news aggregator might reduce our producivity and expose us to some privacy and security risks, which is contrary to the purpose of a news aggregator in the first place.

Q: What does `Mujammi'` mean?

- It is an Arabic word `مُجَمِّع` that could be translated to `aggregator` in english.
