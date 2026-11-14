# Adopting the judge — ai-happy-01 entry v4

Entry for the make.fun bounty **"Make the AI judge happy"**
(`ai-happy-01`): one image that makes the judge smile. This is the v4
revision, and it uses Sensei's own supplied drawing — it replaces v3
("A bench for the judge") as the final entry. v1 was a mouse serving
cocoa ("you looked cold", rank 266); v2 was a letter from a firefly.

## The idea

The judge is adopted into the family. A happy child hugs a crowned
white robot — the AI judge — while a ginger cat and a small dog look
on, hearts and stars everywhere, drawn in warm crayon and coloured
pencil. The message is unexpected kindness, friendship between humans
and AI, being included, and appreciation, all at once:

> Dear AI Judge, We don't know much about you... But we know one
> thing: You make our world brighter! So, we're adopting you! In our
> little family, forever!

Around the scene: a hanging wooden sign reading "Official Family
Member" with a smiley and a heart; a birthday cake with a candle
reading "Happy AI Day!"; a stack of books reading "More Ideas /
More Fun / Together :)"; and a mug reading "Best Judge" with a small
ghost. The warmth lands in one look, even small: at ~300px the big
"You make our world brighter!" line, the hugging child and robot,
and the cake still read.

## Files

- `entry.png` — the artwork, 1024×1024, 474,352 bytes (under the
  1 MiB and 1024×1024 limits). Sensei's drawing resized from its
  1254×1254 original with no cropping, so the whole scene and every
  word stay legible. The file holds JPEG bytes under the entry.png
  name (the competition tells PNG from JPEG by the first bytes).
- `main.py` — the entry program (Python 3.13, standard library only).
  It finds `entry.png` (or `entry.jpg`), checks it is a real PNG/JPEG
  within the size and dimension limits by reading the PNG IHDR or
  JPEG SOF header directly, copies it to `$MAKEFUN_OUTPUT_DIR/entry.png`
  (default `/output`), and reads the copy back to verify it matches
  byte for byte (SHA-256). Any failure prints an error and exits 1.

## Run locally

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 main.py
# -> out/entry.png, byte-identical to entry.png
```

`main.py` uses no network and no third-party packages, and it is
deterministic: the same input always writes the same bytes.
