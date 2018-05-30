# Step 1: Structuring Project

Please prepare the following:

1. Bring your own project which needs to be "cleaned up" or "packaged" for public distribution, or
2. Start an example project to practice with this workshop.
   To avoid confusion of PyPI users, prefix its name with `"pycon-apac2018-sample-"` if you wish to try the real PyPI deployment, though I'd suggest skipping it if you are making a pacakge for the pure practice purpose.

I will assume that you are using GitHub throughout this workshop,
but if you prefer others such as BitBucket it's fined to use them.

Restructure or create the following structure, by starting with empty files.
Note that this is the most common style in Python-based open source projects.

```
ROOT
 +- mypackage
 |  +- __init__.py
 |  +- mymodule.py
 +- setup.py
 +- setup.cfg
 +- .editorconfig
 +- .gitignore
 +- requirements.txt
 +- README.{md|rst}
```

## Good-to-have files

* `.gitignore` – to exclude specific files/dirs from Git's version tracking ([docs](https://git-scm.com/docs/gitignore))
* `.editorconfig` – to use consistent editor settings for all your collaborators who clone the repository ([reference](https://editorconfig.org/))
* `setup.cfg` – A central place to have configurations for setup commands ([docs](https://docs.python.org/3/distutils/configfile.html)) and common CI tools such as pytest and flake8.
