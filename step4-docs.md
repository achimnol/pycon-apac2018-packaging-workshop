# Step 4: Documentation

It is also important to have a nice-looking documentation for your package users.

As you may already know [Sphinx](http://www.sphinx-doc.org/) is the standard tool to generate documentations and [ReadTheDocs](https://readthedocs.org/) is where to publish them.

Usually, documentations are kept inside `docs` directory.
You can initialize its content using `sphinx-quickstart` command after installing Sphinx in your project environment.

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

Of course do not forget to add `sphinx` to `setup.py` (maybe as "docs" extras) and/or `requirements.txt` (as `requirements-docs.txt`) so that CI service or ReadTheDocs can auto-install dependencies for building documentation with appropriate configurations.

**NOTE:** This workshop does not cover details of writing Sphinx docs.
Just write some dummy documentation in `index.rst` skip publishing to ReadTheDocs for workshop practice!
