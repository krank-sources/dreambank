# CHANGELOG

## v1

This is a major update that changes infrastructure from a Python package with downloading functions to a single notebook that scrapes just the raw HTML files for uploading to Zenodo.

* The `raw/` directory is now a self-contained location for raw HTML extraction.
    - Raw HTML is extracted in a single [notebook](./raw/prepare.ipynb).
    - Raw HTML output is saved in the repository in a single zip file and attached as an asset to GitHub releases.
    - The HTML extraction is self-correcting in that it will update the registry with new hashes should the data change.

* Removed all packaging aspects (not a package anymore).
* Removed all online documentation aspects.
* Replaced `src/dreambank/data/registry-source.yaml` with `raw/registry.json`. It now gets automatically updated with new hashes if a file/page changed.
* Removed `datasets/` and `src/dreambank/data/registry.yaml` because the repository no longer extracts data files from HTML (and that's what those represented). That is now done elsewhere.
* Now exports a raw HTML zipped folder in `raw/` in a folder and optional zipped folder.
* Removed fetching module that would pull files directly from the GitHub repository (now use [`krank`](https://github.com/remrama/krank) instead).
