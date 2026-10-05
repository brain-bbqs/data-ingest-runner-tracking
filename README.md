# Data Ingest (Runner tracking)

A [DataLad](https://www.datalad.org) dataset tracking the provenance of every action the [data ingest runner](https://github.com/brain-bbqs/data-ingest-runner) takes.
[`dispatch.py`](https://github.com/brain-bbqs/data-ingest-task-force/tree/main/dispatch) writes to it, and the runner workflow pushes it here after each run.

## Branches

- `records` is the dataset itself. The runner commits every image change and every conversion and upload there, and only ever adds to it. See [`docs/README.md`](docs/README.md) for its layout.
- `disk-usage` holds the chart below and its CSV. Every run replaces it with a single commit, so it has no history of its own. The CSV has a row per run.
- `main` holds this documentation. Its own copy of the records stops at the switch to `records`.

## Runner disk usage

![Runner disk usage](https://raw.githubusercontent.com/brain-bbqs/data-ingest-runner-tracking/disk-usage/disk-usage.svg)

The full history is in [`disk-usage.csv`](https://github.com/brain-bbqs/data-ingest-runner-tracking/blob/disk-usage/disk-usage.csv).
