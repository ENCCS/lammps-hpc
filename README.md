# LAMMPS on HPC

Short tutorials and reference notes for using LAMMPS on EuroHPC systems.

## Content

- [Episode 1: Installing LAMMPS on EuroHPC](content/short-tutorials/s01e01.md)
- [Episode 2: LAMMPS with MACE on Leonardo Booster](content/short-tutorials/s01e02.md)
- [Episode 3: LAMMPS with EESSI on EuroHPC](content/short-tutorials/s01e03.md)
- [Reference: CUDA driver, toolkit, and compute capability mapping](content/reference/cuda_driver_cuda_cc_mapping.md)

The tutorials previously lived in `short-tutorials/`; the CUDA note previously
lived in `cuda/`. All website sources now live in `content/`.

## Build locally

Use Python 3.13, matching the template and CI configuration:

```bash
python3.13 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install .
make dirhtml SPHINXOPTS="-W --keep-going"
python -m http.server 8000 --directory _build/dirhtml
```

Open <http://localhost:8000>. Build output is ignored by Git. Tutorial code
blocks are displayed as examples; building the documentation does not run
LAMMPS, install MACE, or submit HPC jobs.

For automatic rebuilds during editing, install `sphinx-autobuild` into the
same environment, then run `make livehtml`.

## Add a post or reference note

1. Add a Markdown file under `content/short-tutorials/` or `content/reference/`.
2. Start the page with a unique level-one heading.
3. Add its path, without `.md`, to the appropriate toctree in `content/index.md`.
4. Use standard fenced code blocks such as `bash`, `python`, or `text`.
5. Link to other site pages with MyST document links, for example
   `` {doc}`../reference/cuda_driver_cuda_cc_mapping` `` from a tutorial.
6. Run the strict build above before committing.

Site title, attribution, and repository settings are in `content/conf.py`.
The theme styles and footer assets are in `content/_static/` and
`content/_templates/`.

## CI and publication

`.github/workflows/sphinx.yml` builds directory HTML and single-page HTML on
pushes and pull requests. Warnings fail the build. On pushes and manual runs,
the template workflow publishes to the `gh-pages` branch, with multi-branch
previews enabled. Configure GitHub Pages to serve that branch from its root.
Publication occurs only when the workflow runs on GitHub.

## Template provenance

Adapted from `ENCCS/sphinx-lesson-template`, commit
`b460ac1af94049533a41abdb03ed4c0cf0177f1e` (Improve footer logos in dark mode).
The build configuration, Furo theme, ENCCS branding, funding footer, and
light/dark logo variants originate from that version. The template's Python
3.13 requirement and exported `pylock.toml` are retained. The default local
and CI installation resolves dependencies from `pyproject.toml`.

Template license notices are preserved in `LICENSE` and `LICENSE.code`.
