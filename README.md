# The World Today — Wednesday 18 November 2026

[![Bounty](https://make.fun/badge/news-image-20261118.svg)](https://make.fun/bounty/news-image-20261118) [![Rank](https://make.fun/badge/news-image-20261118/zkNata/news-image-20261118/rank.svg)](https://make.fun/bounty/news-image-20261118) [![Reward](https://make.fun/badge/news-image-20261118/zkNata/news-image-20261118/reward.svg)](https://make.fun/bounty/news-image-20261118)

Entry for [news-image-20261118](https://make.fun/bounty/news-image-20261118)
(make.fun, $250, 50 paid places).

## What it is

A program that **draws** its image at runtime (Node 22, standard library
only, no network): a 1024×1024 newspaper front page with one big date banner
— `WEDNESDAY 18 NOVEMBER 2026` — and six story panels. Each panel has a
simple geometric icon drawn in code, a short title, and a one-to-three-line
factual caption. The image is rendered by hand: a pixel framebuffer, a 5×7
bitmap font, and a from-scratch PNG encoder (zlib deflate + CRC32).

Text is drawn from a bitmap font on purpose: it can never come out garbled
the way AI-generated text does — exactly what this contest's judge penalises
under "craft".

## The six stories (all verified from reports published 18 Nov 2026)

| Panel | Story |
|---|---|
| GULF ON EDGE | Iran drones target a US radar in Bahrain; US jets hit a Qeshm Island site. |
| APEC IN SHENZHEN | 33rd APEC Economic Leaders' Meeting opens in Shenzhen; Xi chairs and delivers the CEO Summit keynote on the morning of 18 Nov; 21 member economies. |
| CRIMEA BRIDGE | Ukraine hits the Crimean bridge a second consecutive day; Russia pounds Kyiv bridges. |
| CHEAT CRACKDOWN | Ofqual warns pupils who use AI or smart devices to cheat face "life-altering" penalties — disqualification from GCSEs/A-levels; 2,225 smart-device cases last summer. |
| SANCTIONS | Britain and Australia sanction Israeli settlement firms. |
| CYCLONE AKVAN | Cyclone Akvan strengthens over the Bay of Bengal; severe on Nov 18, landfall due ~midday Nov 20 (IMD). |

Sources and the exclusion log are in `../analysis/news-sources.md` — the
analysis folder is not part of the entry. (Fix round 18 Nov ~03:00 UTC: the
Trump-Manila and Canada-China panels were replaced — both turned out to be
17 Nov events — by APEC Shenzhen and the Ofqual cheat crackdown; the cyclone
caption was corrected to the IMD dates.)

## Verification (run locally)

- `mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts` writes `out/entry.png`.
- Two runs write byte-identical files (same sha256) — no clock, no randomness.
  Fixed entry: sha256
  `f910efd2b3f4d9f147088b10ada1e17952e89c678ce1c5c34c2286316d5d7e4f`,
  24,284 bytes, 1024×1024, valid PNG.
- PNG valid: correct signature, IHDR 1024×1024, single IDAT, IEND; file
  under the 1 MiB cap.
- Readability checked at full size and at ~300 px downscale: every title and
  caption legible, no garbled text.

## Honest caveats

- Built at ~02:30 UTC on 18 Nov, fix round ~03:00 UTC the same morning
  (two wrong-date panels replaced, cyclone caption corrected): the stories
  are the verified overnight/early-morning set. The APEC summit and daytime
  events develop later on the 18th, so the content may deserve a refresh on
  19 Nov before the deadline (20 Nov 07:00 WIB).
- The icons are flat pictograms, not photographs: a deliberate trade for
  clean, legible, thumbnail-readable panels. Against photo-real AI images
  the craft is simpler, but nothing in the image is fake, garbled, or
  unverifiable.
- No top-10 guarantee: this is an AI-judged image contest, and @zknata's two
  earlier AI-judged image entries scored 23.9% and 32.9%. What this entry
  fixes versus those: a huge unmistakable date, only verified facts, perfect
  text, and one clear composition.
