# Tidal Cycles

## Tidal Cycles
### [Tutorials](https://tidalcycles.org/docs/patternlib/tutorials/workshop)
### [Reference](https://tidalcycles.org/docs/reference/cycles)
### [Discourse](https://club.tidalcycles.org/)
### [Great Haskell Help](https://learnyouahaskell.com/chapters)

### [MiniTidal/MiniNotation](https://tidalcycles.org/docs/reference/mini_notation)

### new to us from minitidal
- [i make money moves: the meaning(s) of `$` and orbits](https://tidalcycles.org/docs/innards/meaning_of_dollar)
- [operators](https://tidalcycles.org/docs/reference/pattern_structure)

### starting up refresher
    - select your preferred audio output device in AudioMidi Setup
    - open SuperCollider
    - execute `SuperDirt.start;` with shift, return
    - does your preferred audio output device get listed?
    - are they the same sample rate?
    - does it say `SuperDirt: listening to Tidal on port 57120`? (this will take a moment)
    - open a .tidal file in Pulsar
    - execute TidalCycles code with shift, return in Pulsar
    - monitor in Pulsar and SuperCollider post windows
    - (did you already know a little sc? SuperDirt the quark boots sc itself, so please don't boot before using the quark)

## execute
  - shift, return for one line
  - control, return for multiple lines
  - `hush`
  - `# silence`
  - `-- comment`

### mixing and effects
- xfade. orbit is argument.

`d1 $ s "hh*16?"`

`xfade 1 $ s  "909*16?"`

- djf. lpf/hpf with 0-1 argument.

`d1 $ s "hh*16?" # djf sine`

- hbrick. spectral high pass with 0-1 argument.

`d1 $ s "hh*16?" # hbrick sine`

- lbrick. spectral low pass with 0-1 argument.

`d1 $ s "hh*16?" # lbrick sine`

- shape. parametric amplifier with 0-1 argument.

`d1 $ s "hh*16?" # shape sine`

- crush. bitcrush with 1-16 argument

`d1 $ s "wobble" # crush "[4|8|12]"`

- squiz. weird pitchshifter with arguments in multiples of two.

`d1 $ s "wobble" # squiz "[4|8|12]"`

### pattern transformation

- one hit. NO ORBIT!

`once $ s "xmas"`

- slow, hurry

`d2 $ slow 2 $ note (arp "<converge diverge pinkyup pinkyupdown thumbup thumbupdown>" "<d'major a'major>") # s "newnotes"`

- [sometimes and it's cousins](https://tidalcycles.org/docs/reference/randomness/#the-sometimes-family)

- palindrome. reverses pattern every other cycle.

`d2 $ palindrome $ note (arp "<converge diverge pinkyup pinkyupdown thumbup thumbupdown>" "<d'major a'major>") # s "newnotes"`

`d2 $ sometimes (palindrome) $ note (arp "<converge diverge pinkyup pinkyupdown thumbup thumbupdown>" "<d'major a'major>") # s "newnotes"`

- degrade. randomly removes events from a pattern half the time.

`d2 $ degrade $ note (arp "<converge diverge pinkyup pinkyupdown thumbup thumbupdown>" "<d'major a'major>") # s "newnotes"`

`d2 $ sometimes (degrade) $ degrade $ note (arp "<converge diverge pinkyup pinkyupdown thumbup thumbupdown>" "<d'major a'major>") # s "newnotes"`

- degradeBy. randomly removes events from a pattern a specified percentage of the time.

`d3 $ degradeBy 0.3 $ "reverbkick*4"`

- linger. truncates a pattern then repeats the truncation.

`d2 $ linger "[0.25 0.5 0.75]" $ degrade $ note (arp "<converge diverge pinkyup pinkyupdown thumbup thumbupdown>" "<d'major a'major>") # s "newnotes"`

- [chunk'. divides a pattern into parts, applies function to each part, reverses some(that's what the apostrophe at the end is about)](https://tidalcycles.org/docs/reference/alteration/#chunk-1)

`d5 $ chunk' 3 (hurry 2) $ n ("7 2 [3 2] ~") # s "print"`  

- operators a la rachelle with samples (pentatonic clusters + just a *touch* of randomness)

`d5 $ n ("1 ~ 2 [3 2] ~" |+ irand 11) # s "print"`

### samples

- striate. cuts sample into the parameter, plays progressive cut per loop. (can't use with pattern, but we'll get to that with "slice").

`d5 $ striate 3 $ s "print:0 print:1 print:2"`

- begin. where to begin in sample.

`d6 $ s "bev" # begin 0.5`

- end. where to end in sample.

`d6 $ s "bev" # begin 0.5 # end 0.65`

- loop. argument is to stretch the sample over these many patterns, then start again.

`d6 $ loopAt 8 $ s "bev"`

- slice. first argument is how many slices to make of the sample, second argument is which sample to choose per pattern.

`d6 $ slice 16 "[2|4|8|16]" $ s "bev"`

- random slice. argument is how many slices to make of the sample, which one is random.

`d6 $ randslice 8 $ s "bev"`

## yes, you can change bps
`setcps (115/60/4)`

## For next week:
- Make one TidalCycles patch you're proud of to share with the class.
- Document how you made the patch using the "Documentation outline" in the syllabus. Add that documentation and the patch itself to a Markdown file.
- Submit via your lc repo AND Canvas.
