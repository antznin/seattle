# Seattle

Simple website generator that reads the content of `images/` and generates a
minimal and single-threaded website.

No javascript, php, etc. Only HTML/CSS.

## Dependencies

This script depends on [`yattag`](https://www.yattag.org/).

## Usage

```shell
./generate <filename>
```

## `images/`

The `images/` directory must have this format:

```
images
├── 001<Directory name 1>
│   ├── Pic01.jpg
│   ├── Pic02.jpg
│   └── ...
├── 002<Directory name 2>
│   ├── Pic01.jpg
│   ├── Pic02.jpg
│   └── ...
└── ...
```

* Directory names must include a number to sort them by name.

* Pictures are sorted by filenames. Thankfully, most cameras name include a
  `YYYYmmdd` date in the filename.

## Polling script

A simple polling `./poll` script detect changes in `images/` with `inotifywait`,
for automatic updates of the html file when changes happen in that directory.
