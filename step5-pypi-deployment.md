# Step 5: PyPI Deployment

## Building

First install up-to-date `twine` and `wheel` packages into your environment.

```console
$ pip install -U twine wheel
```

Build a source distribution tarball and the binary wheel[^binary]:

```console
$ python setup.py sdist bdist_wheel
```

Then it will use `build` directory as a temporary directory and put the tarball and .whl file into `dist` directory.
It is recommended to exclude these directories from version controls.[^ignore]

[^binary]: If your project includes native modules, they will be contained as compiled binaries. Pure Python sources are included as-is.

[^ignore]: If you have created the project in GitHub and set the default `.gitignore` file provided by GitHub, this is already done.


## Deployment

Create an account in `pypi.org`.
Create a `~/.pypirc` file (under your home directory) and fill your credentials.
Since the password is stored in clear texts, I recommend to use an auto-generated password which is not used in other services.

```dosini
[disutils]
index-servers=pypi

[pypi]
repository = https://upload.pypi.org/legacy/
username = put-yours
password = clear-text-password
```

Then you can now upload your packages to PyPI!

```console
$ twine upload dist/*
```

There is no extra steps to "register" a new project -- just a new package name becomes a new project.
This means that if somebody else has already occupied your package name, you cannot use it unless he/she gives the project ownership or write permission to you in PyPI.
PyPI also restricts re-uploads with the same version number, so when releasing a new version you need to be cautious to avoid re-releases due to simple typos and etc.
