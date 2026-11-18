# THE WORLD TODAY — Tuesday 17 November 2026

[![make.fun](https://make.fun/badge/news-image-20261117.svg)](https://make.fun/bounty/news-image-20261117)
[![rank](https://make.fun/badge/news-image-20261117/zeinrefo-code/news-image-20261117/rank.svg)](https://make.fun/bounty/news-image-20261117)
[![reward](https://make.fun/badge/news-image-20261117/zeinrefo-code/news-image-20261117/reward.svg)](https://make.fun/bounty/news-image-20261117)

Entry for [make.fun bounty **news-image-20261117**](https://make.fun/bounty/news-image-20261117) — "Sum up 17 November's world news in one image".

## The image

A newspaper front page, **"THE WORLD TODAY — TUESDAY 17 NOVEMBER 2026"**, with five stories from that one day, each with a large headline, a one-line summary and a flat drawn illustration:

1. **KERCH BRIDGE PARTLY DOWN** — Ukraine hit the bridge linking Russia to Crimea with missiles and drones; Zelenskyy calls it "unprecedented", Moscow vows to rebuild it. (BBC)
2. **IRAN DRONES HIT US RADAR, BAHRAIN** — Bahrain says its defences shot the drones down; no damage and no injuries reported. (AP / Reuters)
3. **TRUMP LANDS IN MANILA FOR SUMMITS** — Quad talks on Tuesday; the first ever Trump–Xi–Putin meeting set for Thursday in Shenzhen. (NPR / CBS)
4. **US LOSES MEASLES FREE STATUS** — PAHO: 5,412 cases in 2026; status held since 2000 is gone after 26 years. (CDC / PAHO)
5. **NVIDIA BEATS, BUT NO HUANG RETURN** — Sales $115.8bn, up 103%; the board says ex-CEO Jensen Huang will not come back. (BBC / CNN)

Every story happened or was first reported on Tuesday 17 November 2026; the sources are printed in the image footer.

## How it is made

`main.ts` (Node 22, standard library only) draws the image procedurally and writes it to `$MAKEFUN_OUTPUT_DIR/entry.png` (default `/output/entry.png`):

- A hand-written PNG encoder: IHDR/IDAT/IEND chunks, CRC32 implemented from scratch, zlib deflate from Node's stdlib.
- A hand-drawn 5×7 bitmap font defined in code (A–Z, 0–9, punctuation), rendered at large scales so every headline stays legible when the image is viewed at ~300px across.
- All artwork is vector shapes drawn in code: the broken Kerch Bridge over the sea, a radar dish with drones, three flags, a spiked virus, and an AI chip with a rising chart. No image assets, no network, fully deterministic — two runs write byte-identical output.

## Verify

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
```

Output is a 1024×1024 PNG, well under 1 MiB.
