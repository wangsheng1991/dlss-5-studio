# Requirements and compatibility

Everything on this page is either a number we measured or a statement we can point at. Where we do not know, it says unknown instead of guessing.

## Minimum and recommended

| Field | Value | What it actually means |
|---|---|---|
| OS | Windows 10 (1909 or newer, 64-bit) or Windows 11 | 64-bit only. Older Windows 10 builds miss APIs the video encoder path uses. |
| GPU | An NVIDIA RTX GPU, RTX 20 series or newer | The pipeline needs RTX tensor cores. GTX 10 series, GTX 16 series and non-NVIDIA GPUs are outside the supported range. |
| Driver | 610 or newer for hardware NVENC | Below that, encoding falls back to software automatically and the job message says so. Image-only jobs are unaffected. |
| Memory | 8 GB minimum, 16 GB recommended | The recommendation is for 1080p and 4K video. Still images fit comfortably in 8 GB. |
| Disk | About 3 GB free | The portable folder is roughly 1.1 GB unpacked; scratch space during a video job needs the rest. |
| Engine | NVIDIA Visual Enhancer release package | **Not bundled.** Studio drives it as an external component. You install that package yourself, from NVIDIA's own distribution. |

## What "supported" means here, and what it does not

A GPU model being listed as RTX does not by itself prove your machine will run a given job well. We distinguish four states:

- **measured** — we ran the app on that exact card and kept the numbers.
- **supported** — the card is inside the published range, and we have no run of our own on it.
- **below-minimum** — outside the published range; the online converter is the fallback.
- **unknown** — no basis to say either way.

Published requirement tables on other sites usually stop at "supported". The distinction above is the reason our [compatibility checker](https://www.dlss5nvidia.com/dlss-checker) shows four states per feature instead of two.

## The engine dependency

Studio does not ship NVIDIA's enhancer package, and we do not redistribute it. If your engine package is missing or the wrong version, the app reports that at startup instead of failing mid-job.

## Reporting your configuration

Open an issue with:

1. GPU model exactly as reported (for example `RTX 4070 Ti SUPER`), and its VRAM size.
2. Driver version.
3. Windows edition and build number.
4. Job type (style conversion, still image enhancement, video), input size, output size.
5. The job message text, if one appeared.

With those five, a report is checkable. Without them we can only say "unknown", which is what [COMPATIBILITY.md](COMPATIBILITY.md) records for configurations we have not seen.
