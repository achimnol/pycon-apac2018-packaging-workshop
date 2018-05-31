# Step 4: Documentation

It is also important to have a nice-looking documentation for your package users.

As you may already know [Sphinx](http://www.sphinx-doc.org/) is the standard tool to generate documentations and [ReadTheDocs](https://readthedocs.org/) is where to publish them.

## Sphinx

Usually, documentations are kept inside `docs` directory.
You can initialize its content using `sphinx-quickstart` command after installing Sphinx in your project environment.
It will ask many questions about the documentation -- just use defaults for now and you can change those later.

```
ROOT
 +- mypackage
 |  +- ...
 +- docs
 |  +- Makefile
 |  +- conf.py
 |  +- index.rst
 |  +- ...
 +- setup.py
 +- setup.cfg
 +- ...
```

Once it finishes initialization, try `make html` and open `_build/html/index.html` in a web browser.
This is the starting point of your project documentation.

Of course do not forget to add `sphinx` to `setup.py` (maybe as "docs" extras) and/or `requirements.txt` (as `requirements-docs.txt`) so that CI service or ReadTheDocs can auto-install dependencies for building documentation with appropriate configurations.

I recommend to use [autodocs](http://www.sphinx-doc.org/en/master/ext/autodoc.html) to generate the documentation from source codes.
Note that to use autodocs, "mypackage" must be importable by the Sphinx's CLI program, meaning that the package should be installed as editable for development and writing the documentation.

**NOTE:** This workshop does not cover details of writing Sphinx docs.
Just write some dummy documentation in `index.rst` skip publishing to ReadTheDocs for workshop practice!

## ReadTheDocs (RTD)

Connect your GitHub account with RTD account, and then you can import existing GitHub projects.
You can configure the documentation build process, such as which `requirements.txt` file to use and which Python version (2.x or 3.x).
