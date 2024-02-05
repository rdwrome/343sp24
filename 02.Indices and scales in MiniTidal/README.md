# Advanced MiniTidal

## But first... the Reading
  - [Glitch Lich](https://www.youtube.com/watch?v=6oVeKI4q9C0)
  - [OFFAL at ICLC 2016](https://www.youtube.com/watch?v=zmtLDbWXNeI&feature=emb_logo)

## Show and Tell

## more MiniTidal!

### sound bank indicies
- see all the current samples with:
`!localview audiomap`
- `n` for iNdex (unpitched samples) or Note (samples that are or can be pitched) (more on this later)
- if you give a certain number of events and a different number to use for those events from the index, it will try and even it out.
- n for iNdex goes **after** sound; n for Note goes **before** sounds

**eg**

`s "drum:0 drum:1 drum:2 drum:3"` = play drum sample with first index, then second, then third, etc or

`s "drum*4" # n "0 1 2 3"` = sounds same

`s "drum*4" # n "0 1 2"` = not enough values but evens itself out

### notes & scales as clunky sequencers
`n "0 2 4 5" # s "moog"` = notes with numbers

`n "c e g a" # s "moog"` = notes with names, sounds the same as above

`n (scale "bartok" "0 2 4 5") # s "moog"` = special scale notes

`n (run 7) # s "moog"` = hear a run of the whole collection

`s "moog" # n (irand 7)` = randomness with indicies (doesn't work as notes)

#### all the scales
`minPent majPent ritusen egyptian kumai hirajoshi iwato chinese indian pelog prometheus scriabin gong shang jiao zhi yu whole augmented augmented2 hexMajor7 hexDorian hexPhrygian hexSus hexMajor6 hexAeolian major ionian dorian phrygian lydian mixolydian aeolian minor locrian harmonicMinor harmonicMajor melodicMinor melodicMinorDesc melodicMajor bartok hindu todi purvi marva bhairav ahirbhairav superLocrian romanianMinor hungarianMinor neapolitanMinor enigmatic spanish leadingWhole lydianMinor neapolitanMajor locrianMajor diminished diminished2 chromatic`

### chords

`note (arp "updown" "<a'min7 e'dom7>") # s "moog"`

#### all the chords

`major maj aug plus sharp5 six 6 sixNine six9 sixby9 6by9 major7 maj7 major9 maj9 add9 major11 maj11 add11 major13 maj13 add13 dom7 dom9 dom11 dom13 sevenFlat5 7f5 sevenSharp5 7s5 sevenFlat9 7f9 nine eleven 11 thirteen 13 minor min diminish ed dim minorSharp5 msharp5 mS5 minor6 min6 m6 minorSixNine minor69 min69 minSixNine m69 mSixNine m6by9 minor7flat5 min7 flat5 m7flat5 m7f5 minor7 min7 m7 minor7sharp5 min7sharp5 m7sharp5 m7s5 minor7flat9 min7flat9 m7flat9 m7f9 minor7sharp9 m in7sharp9 m7sharp9 m7s9 diminished7 dim7 minor9 min9 m9 minor11 min11 m11 minor13 min13 m13 one 1 five 5 sus2 sus4 seven Sus2 7sus2 sevenSus4 7sus4 nineSus4 ninesus4 9sus4 sevenFlat10 7f10 nineSharp5 9s5 m9sharp5 m9s5 sevenSharp5flat9 7s5f9 m7sharp5flat9 elevenSharp 11s m11sharp m11s`

#### all the arpeggiators

`up down updown downup converge diverge disconverge pinkyup pinkyupdown thumbup thumbupdown`

### time

`slow 2 $ note "c'maj7 f'maj7" # s "moog"` = halftime

`fast 2 $ note "c'maj7 f'maj7" # s "moog"`= doubletime

`every 3 (fast 2) $ note "c'maj7 f'maj7" # s "moog"` = every third cycle, doubletime

`every 2 (rev) $ s "[bd*3] ~ hh*2"` = every second cycle, reverse the pattern

#### time **in terminal!!!**
`!setbpm 90` = change the bpm of bno

#### [to add your own samples](https://github.com/dktr0/estuary/wiki)

## to go EVEN further
- Take a look at the [TidalCycles documentation here](https://tidalcycles.org/docs/reference/), and cross reference it with the definitions in [this Haskell file](https://github.com/dktr0/estuary/blob/dev/client/src/Estuary/Help/MiniTidal.hs) that is up-to-date with what MiniTidal is capable of in Estuary.

## For next week:
- Make one MiniTidal patch you're proud of to share with the class.
- Document how you made the patch using the "Documentation outline" in the syllabus. Add that documentation and the patch itself to a Markdown file you made for this week.
- Submit via your lc Repository AND canvas.

## Recommended but not required
- [Legacy Russell talking about her concept of Glitch Feminism at the School of Visual Arts](https://www.youtube.com/watch?v=DqNPgd5B3io)
