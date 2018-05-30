# Step 7: Towncrier

Towncrier is a person that announces born of new babies loudly in a village.
(e.g., [Birth of royal baby boy for William and Kate](https://www.youtube.com/watch?v=7XsbsKKvpEw))

In Python, [`towncrier`](https://github.com/hawkowl/towncrier) package provides an automated way of managing changelogs when releasing new versions of your packages.
Check out its README on the usage instructions.
The basic concept is to keep one-liner "news fragments" in a specific directory (default: `NEWS`), collect them when releasing, and clean up the directory.

Here are several example projects which utilize `towncrier` decently:

* [aiohttp](https://github.com/aio-libs/aiohttp)
