# beeptune

Output tunes to pcspkr via GRUB's `play` or `beep(1)`.

In particular, `beeptune` allows one to use musical notes
directly when describing tunes, which makes transcribing
sheet music significantly more user friendly.

## usage

Accepts a superset of GRUB's play command's syntax, as follows:

`TEMPO [OUTPUT] [PITCH DURATION_MULTILIER]+`

|          | default  | values       | description & notes                                |
| -------- | -------- | ------------ | -------------------------------------------------- |
| TEMPO    | none     | int          | inverse linear scale: 30=2s, 60=1s, 120=0.5s ...   |
| OUTPUT   | `--beep` | `--grub`     | print GRUB play-formatted tune                     |
|          |          | `--beep`     | play the tune using `beep(1)`                      |
|          |          | `--cmd`      | print baked `beep(1)` command line for the tune    |
| PITCH    | none     | 0<Hz<20000   | pitch of note, in Hz; supports decimals            |
|          |          | 0            | produces a rest                                    |
|          |          | musical note | (for usability); see table in script               |
| DURATION | none     | int          | multiplier for TEMPO; decimals are not unsupported |

Take a look at the [examples page](examples.md).

## contributing

Feel free to contribute.

Transcribed music to put on the [examples page](examples.md) is especially
welcome, as that makes including tunes far easier for others.

## license

(c) 2016 Mustangflyer. GPLv3 (or any later).

Excluded is the table of musical notes to Hz, which is taken from
[this website](http://www.phy.mtu.edu/~suits/notefreqs.html)
and is (c) 1998-2015 B. H. Suits, Physics Department,
Michigan Technological University.
