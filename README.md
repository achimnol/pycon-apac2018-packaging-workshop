# Making a modern Python package

## Tasks and topics

* [Step 1:](step1-structure.md) Setting up a GitHub repository with a recommended directory structure
* [Step 2:](step2-writing-setup.md) Writing the first version of `setup.py` and testing it using virtualenv
* [Step 3:](step3-testing.md) Adding test cases using pytest and setting up Travis CI for automated tests
* [Step 4:](step4-docs.md) Writing a good-looking documentation using Sphinx and readthedocs.io
* [Step 5:](step5-pypi-deployment.md) Deploying to PyPI with twine and Travis CI
  - Ensure you have a canonical, non-overlapping, [CoC](https://www.python.org/psf/codeofconduct/)-compliant package name!
  - For just testing and learning for this workshop, let's use a common prefix for package names: `"pycon-apac2018-sample-"` so that PyPI users don't get confused by "bogus" packages.
* [Step 6:](step6-badges.md) Adding shiny badges to the GitHub README
* [Step 7:](step7-towncrier.md) Using `towncrier` to automatically keep changelog up-to-date
* [Step 8:](step8-github-extras.md) Provide templates for contributors.

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
