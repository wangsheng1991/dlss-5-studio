# DLSS5 Studio

**The Windows RTX app behind [dlss5nvidia.com](https://www.dlss5nvidia.com/): style conversion and image/video enhancement that runs on your own GPU.**

This repository is the public home of DLSS5 Studio — requirements, release notes, the compatibility record we keep, and the issue tracker. The application itself is not open source and is not distributed from this repository; access is requested on our site.

<p align="center">
  <img src="assets/before-lowres.jpg" width="44%" alt="Before: low-resolution source image">
  <img src="assets/after-upscaled.jpg" width="44%" alt="After: the same image processed by our pipeline">
</p>
<p align="center"><em>Left: the source we were given. Right: the same image after our pipeline. Both are our own output, not an NVIDIA screenshot.</em></p>

---

## What it is

DLSS5 Studio is a portable Windows application that runs a neural style-conversion and enhancement pipeline locally. Two jobs in practice:

| Job | What comes out |
|---|---|
| **Style conversion** | An existing image or frame is redrawn in a target look (lighting, materials, rendering style) instead of being merely sharpened |
| **Enhancement / upscaling** | A low-resolution, soft or compressed source gets detail added and is exported at a target size |

Everything is processed on the machine you run it on. Nothing is uploaded to us, and no account is needed to run a job once the app is installed.

## What it is **not**

This is the part most people arrive confused about, so it is first:

- It is **not** NVIDIA's DLSS 5, and it does not enable DLSS 5 in any game. NVIDIA's DLSS 5 is a game-rendering technology that a game has to integrate; our app cannot install it, emulate it, or unlock it.
- It does **not** make a game render faster, and it has nothing to do with `nvngx_dlss*.dll` or any in-game frame generation.
- It is not affiliated with, endorsed by, or sponsored by NVIDIA. "DLSS", "RTX" and "GeForce" are NVIDIA trademarks; we use them only to state hardware and compatibility facts.
- It does **not** bundle NVIDIA's Visual Enhancer release package. Studio drives that engine as an external component; see [REQUIREMENTS.md](REQUIREMENTS.md).

If what you actually want is NVIDIA's in-game feature, our site keeps a source-dated tracker instead: [DLSS 5 games](https://www.dlss5nvidia.com/games) and [which GPUs are in scope](https://www.dlss5nvidia.com/dlss-checker).

## Requirements

| | |
|---|---|
| OS | Windows 10 (1909 or newer, 64-bit) or Windows 11 |
| GPU | An NVIDIA RTX GPU — RTX 20 series or newer |
| Driver | 610 or newer for hardware NVENC encoding. On an older driver the encoder falls back to a software codec automatically and says so in the job message |
| Memory | 8 GB minimum; 16 GB recommended for 1080p and 4K video |
| Disk | About 3 GB free — the portable folder is roughly 1.1 GB unpacked |
| Engine | The NVIDIA Visual Enhancer release package. Studio drives it — it is not bundled inside this download |

No RTX GPU, or the local build does not fit your machine? The browser converter runs the same pipeline online: <https://www.dlss5nvidia.com/visual-enhancer>.

## One measured run

We publish numbers only when we ran them ourselves.

> **Windows 11 Pro, RTX 4090 24 GB, driver 591.86** — 720p source → 2560×1440 H.264 MP4 in **87.4 s** (2.43 s/frame; software encode on that driver).

That is one batch result on one machine, recorded 2026-09-25. It is not real-time performance, not a comparison between GPUs, and not a game benchmark. Our measurement rules and the fields we require for every run are on the [benchmark evidence page](https://www.dlss5nvidia.com/benchmark).

## Getting access

Access is requested, not downloaded from here: <https://www.dlss5nvidia.com/download>. You file a request on that page, we reply by email with the build and the checksums. There is no public direct-download link, and we do not mirror other people's packages.

## This repository

- [REQUIREMENTS.md](REQUIREMENTS.md) — the full compatibility statement and what each field means.
- [CHANGELOG.md](CHANGELOG.md) — dated record of what changed in the app.
- [COMPATIBILITY.md](COMPATIBILITY.md) — the compatibility reports we have received, and the rule that a model name alone is not proof.
- **Issues** — bug reports and compatibility reports. If you file a compatibility report, say the exact GPU model, driver version, Windows build and what you ran; that is what makes the report usable.

We read issues, and a report that reproduces gets fixed faster than a report that does not.

## Links

| | |
|---|---|
| Site | <https://www.dlss5nvidia.com/> |
| Download and access request | <https://www.dlss5nvidia.com/download> |
| GPU compatibility table (source-dated) | <https://www.dlss5nvidia.com/dlss-checker> |
| Games tracker | <https://www.dlss5nvidia.com/games> |
| Benchmark rules and limits | <https://www.dlss5nvidia.com/benchmark> |
| Before/after reference cases | <https://www.dlss5nvidia.com/before-after> |

## License

The application is proprietary; all rights reserved. The text and images in this repository are published so that people can evaluate the product, and may be quoted with attribution and a link. See [LICENSE](LICENSE).
