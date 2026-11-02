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

For a game-character style reference without installing Studio, [try the browser sample](https://www.dlss5nvidia.com/dashboard?tool=game-character-style&sample=characterStyle). It is a separate cloud workflow; its output is not a local Studio compatibility test.

## One measured run

We publish numbers only when we ran them ourselves.

> **Windows 11 Pro, RTX 4090 24 GB, driver 591.86** — 720p source → 2560×1440 H.264 MP4 in **87.4 s** (2.43 s/frame; software encode on that driver).

That is one batch result on one machine, recorded 2026-09-25. It is not real-time performance, not a comparison between GPUs, and not a game benchmark. Our measurement rules and the fields we require for every run are on the [benchmark evidence page](https://www.dlss5nvidia.com/benchmark).

## Getting access

The **local Windows RTX Studio beta** has a separate [application page](https://www.dlss5nvidia.com/studio-beta). Sign in and request access there; invitations are handled by email. This repository does not publish a public Studio installer.

For an installer you can download now, **DLSS5 Enhance** is a separate open-source cloud client:

| Platform | Direct download |
|---|---|
| Windows x64 | [Enhance v0.1.1 EXE](https://github.com/wangsheng1991/dlss5-enhancer-cli/releases/download/v0.1.1/DLSS5.Enhance-0.1.1-win-x64-Setup.exe) |
| macOS Intel | [Enhance v0.1.0 DMG](https://github.com/wangsheng1991/dlss5-enhancer-cli/releases/download/v0.1.0/DLSS5.Enhance-0.1.0.dmg) |

Downloading these unsigned previews needs no email or sign-in. Running Enhance cloud jobs requires internet access, a website account and credits; local RTX hardware is not required. Enhance is not the local Studio app and does not include its image/video engine. [Release notes, checksum and native Windows test screenshot](https://github.com/wangsheng1991/dlss5-enhancer-cli/releases/tag/v0.1.1).

[All downloads, online trial and beta application](https://www.dlss5nvidia.com/download).

## Windows character-style development

The planned next workflow for the **separate cloud client** is: choose a game-character image, pick one of the five browser styles, confirm the credit cost, generate, compare and save. Current Enhance Windows v0.1.1 still supports batch image enhancement; character styling has not shipped in that client.

- [Developer requirements and native Windows acceptance checklist](https://github.com/wangsheng1991/dlss5-enhancer-cli/blob/master/docs/WINDOWS-CHARACTER-STYLE-20261102.md)
- [Implementation tracking issue](https://github.com/wangsheng1991/dlss5-enhancer-cli/issues/1)
- [Shared style/API catalog](https://www.dlss5nvidia.com/desktop/character-style-v1.json)

The cloud-client plan does not change this local RTX Studio beta's runtime, hardware requirements or access process. [Try character styling in the browser now](https://www.dlss5nvidia.com/dashboard?tool=game-character-style&sample=characterStyle).

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
| Published downloads and online trial | <https://www.dlss5nvidia.com/download> |
| Local Windows RTX beta application | <https://www.dlss5nvidia.com/studio-beta> |
| GPU compatibility table (source-dated) | <https://www.dlss5nvidia.com/dlss-checker> |
| Games tracker | <https://www.dlss5nvidia.com/games> |
| Benchmark rules and limits | <https://www.dlss5nvidia.com/benchmark> |
| Before/after reference cases | <https://www.dlss5nvidia.com/before-after> |

## License

The application is proprietary; all rights reserved. The text and images in this repository are published so that people can evaluate the product, and may be quoted with attribution and a link. See [LICENSE](LICENSE).

## Related

- [dlss5-enhancer-cli](https://github.com/wangsheng1991/dlss5-enhancer-cli) — Batch image enhancement from your own machine — the command-line client for the web enhancer.
- [dlss5-visual-enhancer](https://github.com/wangsheng1991/dlss5-visual-enhancer) — Reproduce one documented enhancement example locally: input, output, hashes, compare page.
- [dlss5-compatibility-data](https://github.com/wangsheng1991/dlss5-compatibility-data) — Source-attributed, machine-readable DLSS 5 GPU compatibility data.
- [DLSS5NVIDIA](https://www.dlss5nvidia.com/) — the site these projects belong to
