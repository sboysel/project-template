# src

Project source code

## Modules

The key idea is to organize project code into *modules*, which are subdirectories of `src`. The exact set of modules will depend on you specific project and you should feel free to experiment with this framework to find the organizational pattern that works best for your use case. One handy pattern is to keep utility code used across the project in a module named `lib`, testing code in `test`, and the main project code under `modules`.

```
src
├── lib          # utility code used project-wide
├── modules      # project modules
│   ├── bar
│   ├── baz
│   └── foo
├── test         # unit tests, snity checks
├── HEADER       # License header: include with each source code file
└── README.md   
```

## Example

```
src
├── lib
│   ├── __init__.py
│   └── utils.py
├── modules
│   ├── core
│   │   ├── __init__.py
│   │   ├── build.py
│   │   ├── figures.py
│   │   ├── regressions.py
│   │   └── similations.jl
│   ├── mechanisms
│   └── robustness
├── test
│   ├── __init__.py
│   └── test_core.py
├── HEADER
└── README.md

7 directories, 11 files
```

Call source code from the top-level project directory. For example, using GNU Make as a build script

```make
.PHONY: all

all: core

core: data/output/sample.csv
  python -m src.modules.core.regression

data/output/sample.csv: src/modules/core/build.py
  python -m src.modules.core.build
  
output/figures/figure1.png: src/modules/core/figures.R data/output/sample.csv
  Rscript src/modules/core/figures.R

simulations: src/modules/core/similations.jl
  julia src/modules/core/similations.jl
```

## Licensing

Include `HEADER` as a top level comment in each source code file. Modify the `Description:` field to reflect what the file does.
