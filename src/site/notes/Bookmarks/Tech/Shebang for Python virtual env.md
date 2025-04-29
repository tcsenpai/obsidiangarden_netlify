---
{"dg-publish":true,"permalink":"/bookmarks/tech/shebang-for-python-virtual-env/","tags":["coding","tutorial","wow"]}
---


env

## Addendum

- Install `uv` on Linux/MacOS
  - `curl -LsSf https://astral.sh/uv/install.sh | sh`
- Install `uv` on Windows
  - `powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`

### Using pip/pipx

`pip install uv`
`pipx install uv`

## Main post

**[#!/usr/bin/env -S uv run](https://github.com/alsuren/sixdofone/blob/43a73c4b9d60904fceb4ed0418178ca0bd1a663d/app.py)** ([via](https://twitter.com/charliermarsh/status/1826008669131067757)) This is a really neat pattern. Start your Python script like this:

```
#!/usr/bin/env -S uv run
# /// script
# requires-python = ">=3.12"
# dependencies = [
#     "flask==3.*",
# ]
# ///
import flask
# ...

```

And now if you `chmod 755` it you can run it on _any machine_ with the `uv` binary installed like this: `./app.py` - and it will automatically create its own isolated environment and run itself with the correct installed dependencies and even the correctly installed Python version.

All of that from putting `uv run` in the shebang line!

Code from [this PR](https://github.com/alsuren/sixdofone/pull/8) by David Laban.
