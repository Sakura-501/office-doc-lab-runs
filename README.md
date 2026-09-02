# office-doc-lab-runs

Run logs and captured outputs from automated Microsoft Word document-processing tests
executed on GitHub Actions (`windows-latest` x64 runners). Crafted Word97 binary documents
are parsed by Word in a clean runner environment, and internal buffers are captured at a
defined code point (the section-property translation routine) for cross-run comparison.

## Contents

- `runs/20260901/` - two crafted-document probe runs + one control run (full runner logs,
  breakpoint-capture transcripts) and a byte-level differential of the captured buffers.
- `runs/20260902/` - same-build repeat of the probe runs (capture transcripts) plus a
  five-file automation ladder transcript.

## Environment

Microsoft 365 Current Channel Preview, build 16.0.20326.20100, installed per-run by the
Office Deployment Tool inside each job. Nothing persists between runs.

## What the captures show

The captured source buffers contain the input record header (`3B 00`) and record body
verbatim at the routine entry. Consumption continues past the declared record length
(59 bytes); the tail bytes differ between the two crafted runs, separating input bytes
from environment (non-input) memory. See `runs/20260901/oob_differential_analysis.txt`
for the byte-level comparison.
