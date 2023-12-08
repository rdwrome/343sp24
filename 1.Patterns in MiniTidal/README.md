# Patterns in MiniTidal

### Headphones?

### Reading:
  - "Sonic Presence and Performative Attention" - Trueman
    - Localisation
    - Virtuousity
    - Performance practice
    - "Tinkering"
  - "Conducting the Laptop Orchestra"
    - "Responsive Battleship"
  - '"as far as I could tell, they were all just checking their email"'

## [Estuary](https://estuary.mcmaster.ca/)
- Sandbox
- What's great
  - so accessible
- What's not so great
  - limited functionality
- [Estuary Discord](https://discord.com/invite/snvFzkPtFr)

## MiniTidal
- Everything is pattern-based
  - [NOT BPM!](https://tidalcycles.org/docs/patternlib/tutorials/cycles)
- Based on [TidalCycles](https://tidalcycles.org/)
  - In TidalCycles everything is pattern-based, too
- Use the samples in the sandbox (we'll get to more complicated samples later)

## BNO
#### change grid **in terminal!!!** with `!presetview twobyfive` to see everyone

### starter drum samples

`bd sd hh ho hc lt ht mt cp`

### starter pattern commands and syntax
`s` = sound

`" "` = what to fit inside one cycle

`~` = silence

`*` = repeat

`"[ ] "` = what to fit inside one pulse within one cycle

**starter examples**

`s "bd"`

`s "bd hh"`

`s "bd ~ hh"`

`s "bd ~ hh*2"`

`s "[bd*3] ~ hh*2`

**everybody now in solo mode**

**everybody now in BNO**

### more advanced commands and syntax

`,` = layer these atop one another within one pulse

`/` = play once per cycle specified as integer in the denominator

`|` = randomly choose sample from this list per cycle

`<>` = choose one sample from this list to play per cycle

`?` = random silence

**more examples**

`s "[bd sd, hh hh]"`

`s "bd sd/2 hh/3"`

`s "[bd | sd | hh]*3"`

`s "<bd sd hh>*3"`

`s "hh*16?"`

**everybody now in solo mode**

**everybody now in BNO**

### euclidean and polymetric rhythms

`( , )` = spread this many pulses over this many pulses per cycle

`{ , }` = this pattern against this pattern per cycle

**even more examples**

`s "bd(7,12)"`

`s "{bd bd bd bd, cp cp hh}"`

### stacks

`stack [s " ",
s " "]`

**stacks of examples**

`stack [
s "bd(7,12)",
s "{bd bd bd bd, cp cp hh}"
]`

**everybody now in solo mode**

### mix

`# silence`

`# pan`

`# gain`

`# resonance`

`-- comment out`

### periodic oscillators

`sine`

`cosine`

`square`

`tri`

`saw`

`isaw`

**eg**

`# pan sine`

`# gain 0.5`

## For next week:
- Read:
  - Knotts-Changing.pdf here in GitHub!
- Make a Markdown file in your **lc** Repository detailing 2 things that were new to you in the reading and 2 things you already knew in the reading.
- Make one MiniTidal patch you're proud of to share with the class (will be factored into your participation grade next week).
- Submit your MarkDown file through a link from your repository to Canvas.
- Never forget! HEADPHONES ALWAYS (this is the last reminder)
