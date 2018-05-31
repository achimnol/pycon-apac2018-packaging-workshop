# Step 2: Writing Setup

In this step you have to fill your `setup.py` file and `requirements.txt` file.

The role of `setup.py` is to provide metadata for packages and scripts for the installation process (e.g., environment detection).
There are many discussions about changing script-based `setup.py` to a more static, declarative metadata format, but it's the current way of writing Python packages.

A simplest form of `setup.py` is calling `setuptools.setup` function.

```python
from setuptools import setup, find_packages
from pathlib import Path

setup(
    name='mypackage',
    version='0.1.0',
    description='short one-liner description',
    long_description=Path('README.rst').read_text(),
    packages=['mypackage'],
)
```

For the alternative style with "src":

```python
from setuptools import setup, find_packages
from pathlib import Path

setup(
    name='mypackage',
    version='0.1.0',
    description='short one-liner description',
    long_description=Path('README.rst').read_text(),
    packages=find_packages('src'),
    package_dir={'': 'src'},

    # required only for top-level modules
    py_modules=[splitext(basename(path))[0] for path in glob('src/*.py')],
)
```

For more details and information about standard arguments, consult [the official example here](https://github.com/pypa/sampleproject).

To test the package, create [a virtual environment](https://docs.python.org/3/tutorial/venv.html) and install it there as an editable package.


## FAQ: requirements vs. setup

Requirements files are used to express reproducible/repeatable pinned package versions of for a Python environment while setup scripts (`setup.py`) specifies an abstract list of dependent packages.

[Please read the official documentation about this.](https://packaging.python.org/discussions/install-requires-vs-requirements/#requirements-files)

Options:
* Keep them separately: use wide, minimum-required version ranges in `setup.py` and keep concrete specific versions in `requirements.txt`
* Let `setup.py` *read* `requirements.txt` and use it to auto-generate `xxx_requires` arguments

Still both ways are used in the wild, but I prefer the first option because it more clearly separate the meaning of `requirements.txt` and `setup.py`.


## Joongi's Style

Here I introduce my personal setup/requirements role segregation.
This is *NOT* a only-correct way -- just an idea that you can adopt if you like.

By default, my `requirements.txt` file delegates the expression of all dependencies to `setup.py` using editable installation (`-e .`) and tags (bracket'ed words) for extra requirements:

**requirements.txt**:
```
-e .
```

If required, customize it for different purposes (e.g., development installs):

**requirements-dev.txt**:
```
https://github.com/xxx/yyy@develop#egg=yyy
-e .[dev]
```
