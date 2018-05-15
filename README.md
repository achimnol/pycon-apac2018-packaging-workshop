# Making a modern Python package

## Tasks and topics

* Setting up a GitHub repository with a recommended directory structure
* Writing the first version of `setup.py` and testing it using virtualenv
* Adding test cases using pytest and setting up Travis CI for automated tests
* Writing a good-looking documentation using Sphinx and readthedocs.io
* Deploying to PyPI with twine and Travis CI
  - Ensure you have a canonical, non-overlapping, [CoC](https://www.python.org/psf/codeofconduct/)-compliant package name!
  - For just testing and learning for this workshop, let's use a common prefix for package names: `"pycon-apac2018-sample-"` so that PyPI users don't get confused by "bogus" packages.
* Adding shiny badges to the GitHub README
* Using `towncrier` to automatically keep changelog up-to-date

Please come and ask questions related to above topics!
As long as our time allows, I could help you to resolve problems in the packaging and CI setups of your projects.

## Materials

* https://packaging.python.org/tutorials/distributing-packages/ - Put this under your pillow
* https://github.com/pypa/sampleproject - You could start by forking this project!
* https://travis-ci.com
* https://readthedocs.org
* https://pypi.org/project/towncrier/

## Real-world examples with simple and complicated deployments

* https://github.com/achimnol/aiotools
* https://github.com/aio-libs/aiohttp
