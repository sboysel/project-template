# data

Project data outputs and caching for intermediates

```
data/
├── output       # Fully processed data immediately ready for analysis
├── temp         # Intermediate objects from build process
├── LICENSE      # Data-specific license
└── README.md

3 directories, 2 files
```

Objects in `temp` should never be tracked into version control. Objects in `output` *may* be tracked into version control (e.g. if they are small and not subject to licensing restrictions).

## Keep input data separate from project codebase

This project template takes the opinionated stance that *project data and code should be organized separately*. This is in contrast to the common practice of placing any and all project-related data in a `data/` subdirectory of the project codebase. The `data/` directory in this template stores only processed output data (`data/temp`) and intermediate objects (`data/temp`).

### Why?

There are a number of reasons to keep input data separate from the project codebase.

- **Security:** there may be reasons why the data simply cannot be stored within the project folder, let alone on your personal machine.
- **Immutability:** input data should be immutable and should *never* be modified by your analytical code.
- **Redundancy:** things happen when you're mucking about with project analytical code. Keeping data separate helps promote redundancy to mitigate against data loss.
- **Scalability:** as project data scales, it may become infeasible to place it within the project folder.
- **Efficiency:** data that is shared between projects and/or collaborators ought to be placed in a single location, not everyone's personal machine.

### What should I do instead?

Expose paths to input data in `conf/main.toml`. These settings might differ between collaborators, so it's best to keep them in a configuration file.



