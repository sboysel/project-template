# project-template

[![version](https://img.shields.io/badge/version-2024.11-blue)]()
[![data BSD-3-Clause](https://img.shields.io/badge/code-BSD_3--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![data CC-BY-4.0](https://img.shields.io/badge/data-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

## Usage

```shell
git clone --depth=1 https://github.com/sboysel/project-template my-new-project
cd my-new-project
rm -rf .git
git init
```

## Organization

```
project-template/
├── conf              # project configuration files                
│   ├── README.md
│   └── main.toml
├── data              # project data
│   ├── output          # final data output
│   ├── temp            # intermediate data objects
│   ├── LICENSE         # data-specific license
│   └── README.md
├── doc               # project documentation and write-up
│   ├── notes
│   ├── paper
│   ├── references
│   ├── slides
│   └── README.md
├── log               # store for log files
├── output            # final project outputs
│   ├── figures
│   └── tables
├── src               # project source code
│   ├── lib             # code shared across modules
│   ├── modules         # project modules
│   │   ├── bar
│   │   ├── baz
│   │   └── foo
│   ├── test            # unit tests, sanity checks, etc.
│   ├── HEADER          # project source code license header
│   └── README.md
├── LICENSE           # project license: BSD-3 for source code, CC-BY-4.0 for data
├── Makefile          # project build script (alternatives: simple scripts, other command runners)
├── README.md         # top-level project README
└── TODO.md           # project TODO list
```

## License

As [suggested by the American Economic Association](https://www.aeaweb.org/journals/data/faq#license):

- source code: BSD-3-Clause
- data: CC-BY-4.0
