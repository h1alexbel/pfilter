# pfilter

[![EO principles respected here](https://www.elegantobjects.org/badge.svg)](https://www.elegantobjects.org)
[![DevOps By Rultor.com](http://www.rultor.com/b/h1alexbel/pfilter)](http://www.rultor.com/p/h1alexbel/pfilter)
[![We recommend IntelliJ IDEA](https://www.elegantobjects.org/intellij-idea.svg)](https://www.jetbrains.com/idea/)

`pfilter` is a command-line tool for filtering your [CSV] dataset by [percentiles][Percentile].

**Motivation**. During the work on [CaM] project, we were required to filter
out [too small and too big GitHub repositories by number of files][cam-issue].
No readily available command-line tool existed that could perform that
function, so we created `pfilter`.

## How to use

First, pull it from [PyPI][PyPI-repo] like this:

```bash
pip install pfilter
```

Now, execute it with the following flags:

```bash
pfilter --csv=foo.csv --c=age --lower=0.05 --upper=0.95 --o=filtered.csv
```

Where, `--csv` is a path to your source CSV file, `--c` is a column to filter by,
`--lower` is a lower percentile (max is 1, so 0.05 is a 5th percentile, or P5
for short), `--upper` is an upper percentile (max is 1, so 0.95 is a 95th
percentile, or P95 for short), and `--o` is a location for the output, filtered
dataset.

## How to contribute

Fork repository, make changes, send us a [pull request][guidelines]. We will
review your changes and apply them to the `master` branch shortly, provided
they don't violate our quality standards. To avoid frustration, before sending
us your pull request please run full build:

```bash
poetry build
```

You will need [Python 3.11+]
installed.

[Python 3.11+]: https://www.python.org/downloads/release/python-3110
[CSV]: https://en.wikipedia.org/wiki/Comma-separated_values
[Percentile]: https://en.wikipedia.org/wiki/Percentile
[CaM]: https://github.com/yegor256/cam
[cam-issue]: https://github.com/yegor256/cam/issues/228
[guidelines]: https://www.yegor256.com/2014/04/15/github-guidelines.html
[PyPI-repo]: https://pypi.org/project/pfilter
