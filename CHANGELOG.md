# CHANGELOG

## v1

This is a major update that changes infrastructure from a Python package with downloading functions to a structure like those in the [krank sources collection](https://github.com/krank-sources).

* A `raw/` directory where a single [notebook](./raw/prepare.ipynb) downloads the raw HTML files from [DreamBank](https://dreambank.net), which get uploaded as a GitHub artifact to any release that involves a fresh HTML download (major versions).
* A top directory where a single [notebook](./prepare.ipynb) parses the HTML into two tabular CSV files, `datasets.csv` and `dreams.csv`, which get uploaded as a GitHub artifact to any release that involves a fresh parsing process (minor versions).
* Subdirectories for individual corpora that each have a particular notebook for compiling the respective corpus into a krank-ready corpus. These are not attached as GitHub artifacts but uploaded to Zenodo archives. These are not necessarily the same datasets that DreamBank provides, but custom groupings.

### More detail

* Removed all packaging aspects (not a package anymore).
* Removed all online documentation aspects.
* Replaced `src/dreambank/data/registry-source.yaml` with `raw/registry.json`. It now gets automatically updated with new hashes if a file/page changed.
* Removed `datasets/` and `src/dreambank/data/registry.yaml` because the repository no longer extracts data files from HTML (and that's what those represented). That is now done elsewhere.
* Now exports a raw HTML zipped folder in `raw/` in a folder and optional zipped folder.
* Removed fetching module that would pull files directly from the GitHub repository (now use [`krank`](https://github.com/remrama/krank) instead).
* The `raw/` directory is now a self-contained location for raw HTML extraction.
    - Raw HTML is extracted in a single [notebook](./raw/prepare.ipynb).
    - Raw HTML output is saved in the repository in a single zip file and attached as an asset to GitHub releases.
    - The HTML extraction is self-correcting in that it will update the registry with new hashes should the data change.
