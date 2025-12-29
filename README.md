# dreambank

A repository for curating datasets from [DreamBank](https://dreambank.net).

The raw data is available as HTML and tabular CSV formats via GitHub assets attached to relevant releases. The curated datasets (highly recommended) are available via [`krank`](https://remrama.github.io/krank) or as direct CSV downloads from the [krank Zenodo community](https://zenodo.org/communities/krank).

If you use any of these datasets for publication, cite the original DreamBank paper:

> Domhoff, G. W., & Schneider, A. (2008). Studying dream content using the archive and search engine on DreamBank.net. _Consciousness and Cognition_, 17(4), 1238-1247. doi:[10.1016/j.concog.2008.06.010](https://doi.org/10.1016/j.concog.2008.06.010)

## Repository structure

In processing order:

* A `raw/` directory where a single [notebook](./raw/prepare.ipynb) downloads the raw HTML files from [DreamBank](https://dreambank.net), which get uploaded as a GitHub artifact to any release that involves a fresh HTML download (major versions).
* A top directory where a single [notebook](./prepare.ipynb) parses the HTML into two tabular CSV files, `datasets.csv` and `dreams.csv`, which get uploaded as a GitHub artifact to any release that involves a fresh parsing process (minor versions).
* Subdirectories for individual corpora that each have a particular notebook for compiling the respective corpus into a krank-ready corpus. These are not attached as GitHub artifacts but uploaded to Zenodo archives. These are not necessarily the same datasets that DreamBank provides, but custom groupings.


## Contributing

Post questions, ideas, bugs, and requests for new datasets or features on the [Issue board](https://github/com/krank-sources/issues).

## Versioning

Follows semver major.minor.patch structure where:

* Major releases involve changes to HTML output
* Minor releases involve changes to tabular DreamBank output
* Patch releases involve changes to sub-corpora output (or any other non-functional changes)

## Related projects

Similar projects that I browsed while developing this code:

* [mattbierner/DreamScrape](https://github.com/mattbierner/DreamScrape)
* [josauder/dreambank_visualized](https://github.com/josauder/dreambank_visualized)
* [MigBap/dreambank](https://github.com/MigBap/dreambank)
* [jjcordes/Dreambank](https://github.com/jjcordes/Dreambank)
