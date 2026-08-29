# Geo4D Benchmark Metrics

Public, aggregate-only benchmark results for Geo4D video generation methods.

The published site intentionally contains no videos, per-case records, local
filesystem paths, execution logs, model paths, or credentials. `metrics.json`
is overwritten whenever a new audited benchmark result is published.

## Files

- `index.html`: sortable and filterable aggregate quality, pose, VBench 1.0,
  and VBench 2.0 metrics tables.
- `metrics.json`: sanitized single source of truth consumed by both the public
  page and the private local full report.
- `.nojekyll`: serves the static files directly through GitHub Pages.

## Update from the evaluation server

```bash
cd <geodynvs_eval checkout>
python -m evaluation.export_public_metrics \
  --output <Geo4D_Report checkout>
```

The exporter fails if the public payload contains a server path, Hugging Face
token pattern, log path, or MP4 path. Review the diff, commit, and push; the
GitHub Pages workflow can then deploy the updated static site.
