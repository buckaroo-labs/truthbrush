# truthbrush
Truthbrush is an API client for Truth Social. Truthbrush is built and maintained by the [Stanford Internet Observatory](https://io.stanford.edu). This fork is modified to enable commented-out functionality regarding following/followers.

Currently, this tool can:

* Search for users, statuses, or hashtags
* Pull a user's statuses
* Pull a user's followed accounts
* Pull a user's following accounts
* Pull the list of "People to Follow" or suggested users
* Pull "trending" hashtags
* Pull "trending" Truth posts
* Pull ads
* Pull a user's metadata

Truthbrush is designed for academic research, open source intelligence gathering, and data archival. It pulls all of the data from the publicly accessible API.

## Installation

Truthbrush is not yet available on PyPI. To install it, run `pip install git+https://github.com/buckaroo-labs/truthbrush.git`, or clone the repository and run `pip3 install .`. Provided your `pip` is setup correctly, this will make `truthbrush` available both as a command and as a Python package. **Note that Truthbrush requires Python 3.9 or higher.**

After installation, you will need to set your Truth Social username and password as environmental variables.

`export TRUTHSOCIAL_USERNAME=foo`

`export TRUTHSOCIAL_PASSWORD=bar`

You may also set these variables in a `.env` file in the directory from which you are running Truthbrush.

## CLI Usage

```text
Usage: truthbrush [OPTIONS] COMMAND [ARGS]...

Options:
  --help     Show this message and exit.


Commands:
  search       Search for users, statuses or hashtags.
  statuses     Pull a user's statuses.
  suggestions  Pull the list of suggested users.
  tags         Pull trendy tags.
  trends       Pull trendy Truths.
  ads          Pull ads.
  user         Pull a user's metadata.
``````

**Search for users, statuses, or hashtags**

```bash
truthbrush search --searchtype [accounts|statuses|hashtags] QUERY
```

**Pull all followers for a user**

```bash
truthbrush followers HANDLE
```

**Pull all following for a user**

```bash
truthbrush following HANDLE
```

**Pull all statuses (posts) from a user**

```bash
truthbrush statuses HANDLE
```

**Pull "People to Follow" (suggested) users**

```bash
truthbrush suggestions
```
**Pull trendy tags**

```bash
truthbrush tags
```
**Pull ads**

```bash
truthbrush ads
```

**Pull all of a user's metadata**

```bash
truthbrush user HANDLE
```

## Contributing

Contributions are encouraged! For small bug fixes and minor improvements, feel free to just open a PR. For larger changes, please open an issue first so that other contributors can discuss your plan, avoid duplicated work, and ensure it aligns with the goals of the project. Be sure to also follow the [code of conduct](CODE_OF_CONDUCT.md). Thanks!

Development setup (ensure you have [Poetry](https://python-poetry.org/) installed):

```sh
poetry install
poetry shell
truthbrush --help # will use your local copy of truthbrush
```


If you prefer not to install Poetry in your root environment, you can also use Conda:

```sh
conda create -n truthbrush-env python=3.9
conda activate truthbrush-env

conda install -c conda-forge poetry
poetry install
```

To run the tests:

```sh
pytest

# optionally run tests with verbose logging outputs:
pytest --log-cli-level=DEBUG -s
```

Please format your code with `black`:

```sh
black .
```

## Wishlist

Support for the following capabilities is planned:

- ...nothing right now! (Got an idea? Submit an issue/PR!)
