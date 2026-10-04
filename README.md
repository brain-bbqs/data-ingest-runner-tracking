# Data Ingest (Runner tracking)

A [DataLad](https://www.datalad.org) dataset tracking the provenance of every action the [data ingest runner](https://github.com/brain-bbqs/data-ingest-runner) takes.
[`dispatch.py`](https://github.com/brain-bbqs/data-ingest-task-force/tree/main/dispatch) writes to it, and the runner workflow pushes it here after each run.

<!-- runner-disk-usage:start -->
## Runner disk usage

![Runner disk usage](disk-usage.svg)

Updated by every ingest run from `df` on the drive holding the runner's work directory. The full history is in [`disk-usage.csv`](disk-usage.csv).
<!-- runner-disk-usage:end -->
