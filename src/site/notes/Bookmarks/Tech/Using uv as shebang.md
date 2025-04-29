---
{"dg-publish":true,"permalink":"/bookmarks/tech/using-uv-as-shebang/","tags":["coding","dev","lifehack","productivity","work"]}
---


## 1. Defining Python dependencies at the top of the file

Essentially, we can now put a special comment block at the top of the file, before our import statements like this:

```
# /// script
# requires-python = ">=3.11"
# dependencies = [
#   "flickrapi",
# ]
# ///
```

The Python version is optional and we could specify a specific version constraint on each package should we wish to.

Now, when we run with [uv](https://docs.astral.sh/uv/), uv will ensure that the flickrapi package is installed for us.

```
$ uv run sync-flickr-dates.py
Reading inline script metadata from: sync-flickr-dates.py
Installed 10 packages in 13ms
usage: sync-flickr-dates.py [-h] photo_ids
```

In this case, uv will create a Python 3.12 venv for us. For me this is in ~/.cache/uv (which you can find via uv cache dir).

## 2. uv shebang for those files

As ~/bin is on my path, I want to run the script by calling it directly on the command line. To do this, I use this shebang:

```bash
#!/usr/bin/env -S uv run --script
```

The command line will now run uv run --script and pass the file as the argument. uv ignores the shebang and then runs the rest of the file as a normal Python file.

Once I’ve ensured that that script has executable permissions via chmod a+x {filname}, I’m now good to go with simple command line scripts written in Python that automatically handle their dependencies!
