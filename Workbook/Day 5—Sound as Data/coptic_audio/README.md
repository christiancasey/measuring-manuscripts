# coptic_audio — drop the vowel clips here

The Coptic vowel demo in Day 5 (and in the teaser) loads recordings of the Coptic
vowels, measures their first two formants, places each vowel letter on the vowel
chart, and tests whether that placement could have happened by chance. The
recordings are not in the repo yet. Put them here.

## What to add

Name each file by its vowel. The eight vowels and their file stems:

| stem      | vowel | stem        | vowel |
| --------- | ----- | ----------- | ----- |
| `iota`    | ⲓ     | `omicron`   | ⲟ     |
| `eta`     | ⲏ     | `upsilon`   | ⲩ     |
| `epsilon` | ⲉ     | `omega`     | ⲱ     |
| `alpha`   | ⲁ     | `ou`        | ⲟⲩ    |

There are two levels, depending on how much you want to show.

**1. The chart (one clip per vowel).** Name them `iota.wav`, `alpha.wav`, and so
on. Enough to place each letter on the vowel chart, which is the headline result.

**2. The dispersion test (a few clips per vowel).** To show the placement is not
chance, add a few recordings per vowel, numbered: `alpha_1.wav`, `alpha_2.wav`,
`alpha_3.wav`, and so on. About three per vowel is enough to reproduce the result
(with one per vowel the test is degenerate and is skipped automatically). The code
groups files by the stem before the underscore, so `alpha`, `alpha_1`, `alpha_2`
all count as ⲁ.

## Requirements

- **WAV only** (mono or stereo, any sample rate). To convert from m4a:
  `ffmpeg -i clip.m4a -ar 16000 alpha_1.wav`.
- Each clip should be a clear, fairly steady example of that one vowel: a held
  vowel of about a second, or a single vowel cropped out of a recorded word. Trim
  surrounding silence and consonants where you can. The notebook measures over the
  steady middle of the clip.

## You do not need all eight

The notebook plots whatever files are present and skips the rest. Even three or
four vowels make the chart readable. For a clear triangle, start with the corners:
`iota` (high front), `alpha` (low), and `ou` (high back).
