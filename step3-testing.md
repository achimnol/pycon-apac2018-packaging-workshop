# Step 3: Testing

Whether you use the stdlib's `unittest` package or many people's favorite `pytest`, it is recommended to *automate* execution of test cases.

A common tool for open source projects is [Travis CI](https://travis-ci.com).
Of course you may use your other favorites such as [Circle CI](https://circleci.com/).

First, prepare test cases as normally you do (e.g., add a `tests` directory that contains test modules) and make their execution by a single command such as `python setup.py test`, `python -m pytest`, or `./run-tests.sh`, etc.

Put your test-specific requirements (e.g., pytest and its plugins) into `extra_requires` argument in your `setup.py`, for example:

```python
...

setup(
    ...,
    extra_requires={
	'test': ['pytest', 'pytest-cov', 'pytest-asyncio', ...],
	...
    },
)
```

To automate its execution, register your repository to the CI service so that pushing new commits would trigger a new "build".

For Travis CI, add a new file named `.travis.yml` to the project root.
Have a look at [a good simple example](https://github.com/achimnol/aiotools/blob/master/.travis.yml) which demonstrates two-staged builds of test (executed always) and deployment (executed only for tagged commits when the test succeeds).
You may customize the list of Python versions to test against and combinations of environment variables -- consult [the Travis' documentation](https://docs.travis-ci.com/user/languages/python/).

**NOTE:** This workshop does not cover details of writing test cases.
You can add just a few simple test cases for practice.
