# conf 

Configuration files to store user-specific settings, environment variables, and secrets (e.g. API keys, passwords). Project settings may include filepaths and build flags.

```
conf
├── README.md
├── main.tomli      # Main project settings
└── secrets.toml    # (optional) Sensitive variables. Make sure to add to gitignore
```

## Reading configuration parameters

`src/lib` should include some functionality to read your parameters from configuration files into project code. For exmaple,

```python
import tomllib

def config(path="conf/main.toml") -> dict:
    with open(path, "rb") as f:
        params = tomllib.load(f)
    return params
```

Configuration settings can then be imported as needed in other parts of the project.

```python
from ..lib import config

params = config()
secrets = config("conf/secrets.toml")
```

## Secrets

Sensitive variables such as passwords and API keys ought to be stored in a separate configuration file, i.e. `secrets.toml`. Importantly, `secrets.toml` should *never* be tracked into version control.

```sh
echo "conf/secrets.toml" >> .gitignore
```

Secrets can be imported in the same way as the main configuration parameters.

```python
from ..lib import config

SECRETS = config("conf/secrets.toml")
```

