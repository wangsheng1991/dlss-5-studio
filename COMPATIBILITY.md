# Compatibility record

This file records what we have actually seen and what we have not. It exists so that a model name never gets treated as proof.

## The rule

> A model name is not a compatibility report. A configuration is.

Adding `RTX 4070` to a list tells you nothing about VRAM, driver branch, engine version or the job that was run. So every row below carries who ran it and on what, and a card nobody has run stays **unknown** — not "probably fine".

## States

| State | Meaning |
|---|---|
| `measured` | We ran the app on that exact configuration and kept the numbers |
| `supported` | Inside the published range, with no run of ours on that exact configuration |
| `below-minimum` | Outside the published range; use the online converter |
| `unknown` | No basis for a conclusion either way |

## What we have measured

| Configuration | Job | Result | Recorded |
|---|---|---|---|
| Windows 11 Pro, RTX 4090 24 GB, driver 591.86 | 720p source → 2560×1440 H.264 MP4 | 87.4 s total, 2.43 s/frame, software encode on that driver | 2026-09-25 |

That is the whole of our published local measurement set. One machine, one job type, one date. It is a batch-processing figure, not a real-time claim and not a comparison against another GPU.

## Reports from users

Reports arrive through issues here and through the request form on our site. A report is added to this table only when it names the configuration above; otherwise it is noted as received-but-incomplete and stays `unknown`.

| Date | Configuration | Reported result | State |
|---|---|---|---|
| — | — | No published user configuration yet | — |

This table is deliberately empty rather than filled with plausible entries. When the first checkable report arrives it will appear here with its date.

## Why the table stays small

The temptation with a page like this is to list every RTX card as "supported" and move on. That produces a page that looks complete and is worth nothing: it cannot be falsified, so nobody can act on it. Four states and a dated record is slower to fill and actually usable.

For NVIDIA's own DLSS 5 hardware scope — a different question entirely — see the [DLSS 5 GPU compatibility checker](https://www.dlss5nvidia.com/dlss-checker), which is source-dated per cell and never turns an announcement into a current support claim.
