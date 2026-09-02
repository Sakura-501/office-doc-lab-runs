# Run index

| date | runner | office build | runs | outcome |
|------|--------|--------------|------|---------|
| 2026-09-01 | windows-latest | 16.0.20326.20100 | control + crafted probe x2, breakpoint capture | both crafted probes hit the same routine; control hit a different one |
| 2026-09-02 | windows-latest | 16.0.20326.20100 | crafted probe x2 (repeat) + five-file automation ladder | hits reproduced on the same build; ladder transcript included |
| 2026-09-02 (this repo) | windows-latest | 16.0.20326.20100 | live Actions runs: `doc-lab-capture` + `doc-lab-ladder` | both success; run logs and artifacts visible in the Actions tab above |

## Live runs

The `Actions` tab of this repository contains the complete public runs (workflow `doc-lab-capture`
= breakpoint capture, workflow `doc-lab-ladder` = five-file automation ladder), including full
logs and downloadable artifacts. Verify at: https://github.com/Sakura-501/office-doc-lab-runs/actions

## Files

- `runs/20260901/runner_log_1.txt`, `runner_log_2.txt` - full runner logs (base64 payloads redacted)
- `runs/20260901/oob_differential_analysis.txt` - captured-buffer differential across the two crafted runs
- `runs/20260902/probe_control.txt`, `probe_sepxZ.txt`, `probe_sepxZ-run2.txt` - capture transcripts
- `runs/20260902/grft_rvas.txt` - resolved candidate routine offsets for the build
- `runs/20260902/com_tabcheck_x64_ladder_transcript.txt` - five-file automation ladder transcript
