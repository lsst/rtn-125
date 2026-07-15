[![Website](https://img.shields.io/badge/rtn--125-lsst.io-brightgreen.svg)](https://rtn-125.lsst.io)
[![CI](https://github.com/lsst/rtn-125/actions/workflows/ci.yaml/badge.svg)](https://github.com/lsst/rtn-125/actions/workflows/ci.yaml)

# Photometric Transformation Relations for the LSST Data Preview 2

## RTN-125

This technical note provides photometric transformation relations between the Vera C. Rubin Observatory’s Data Preview 2 (DP2) and other photometric systems. These transformations are derived using both synthetic and empirical data and are intended to support calibration and comparison across survey systems. We present both polynomial equations and lookup-table-based methods, depending on the available data and desired accuracy. The transformations are generally valid for stars with typical spectral energy distributions (SEDs), and caution should be used when applying them to objects with strong emission lines or atypical colors.

**Links:**

- Publication URL: https://rtn-125.lsst.io
- Alternative editions: https://rtn-125.lsst.io/v
- GitHub repository: https://github.com/lsst/rtn-125
- Build system: https://github.com/lsst/rtn-125/actions/


## Build this technical note

You can clone this repository and build the technote locally if your system has Python 3.11 or later:

```sh
git clone https://github.com/lsst/rtn-125
cd rtn-125
make init
make html
```

Repeat the `make html` command to rebuild the technote after making changes.
If you need to delete any intermediate files for a clean build, run `make clean`.

The built technote is located at `_build/html/index.html`.

## Publishing changes to the web

This technote is published to https://rtn-125.lsst.io whenever you push changes to the `main` branch on GitHub.
When you push changes to a another branch, a preview of the technote is published to https://rtn-125.lsst.io/v.

## Editing this technical note

The main content of this technote is in `index.md` (a Markdown file parsed as [CommonMark/MyST](https://myst-parser.readthedocs.io/en/latest/index.html)).
Metadata and configuration is in the `technote.toml` file.
For guidance on creating content and information about specifying metadata and configuration, see the Documenteer documentation: https://documenteer.lsst.io/technotes.
