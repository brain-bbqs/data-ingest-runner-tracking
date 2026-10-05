## Layout

```
envs/<image>.sif                         Container images, annexed (content stays on the runner)
.datalad/config                          Each image's digest-pinned docker:// URL and call format
records/<project>/<UTC stamp>-<step>/    One directory per conversion or upload
  context.json                           Project, dandisets, pinned image, task-force commit, sessions
  info.json, usage.jsonl                 con-duct's run summary and resource usage
  stdout, stderr                         The step's captured output
  manifest.json                          Conversions only: every file written, with its sha256
```

Each record is one commit made by `datalad containers-run`, with DataLad's machine-readable run record in its message.
A failed step is committed too, with `(failed)` in its message.
An image change is its own `[DATALAD] Update containerized environment` commit.

## Reading it

Browse `records/` on the [`records` branch](https://github.com/brain-bbqs/data-ingest-runner-tracking/tree/records/records), or clone it and use `git log`:

```bash
datalad clone https://github.com/brain-bbqs/data-ingest-runner-tracking
cd data-ingest-runner-tracking
git checkout records
git log --oneline -- records/kemere
datalad containers-list
```

The `.sif` images are not on GitHub.
`datalad containers-add --update <name>` with the URL from `datalad.containers.<name>.updateurl` in `.datalad/config` rebuilds one locally, given Apptainer.
