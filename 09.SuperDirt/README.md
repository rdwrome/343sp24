# SuperDirt

## Recording
```SuperCollider
s.record;
s.stopRecording;
```

## [Multichannel](https://tidalcycles.org/docs/configuration/AudioConfig/audio_outputs/)
```SuperCollider
(
s.options.numBuffers = 1024 * 256;
s.options.memSize = 8192 * 32;
s.options.maxNodes = 1024 * 32;
s.options.numOutputBusChannels = 4; // total number of channels output
s.options.numInputBusChannels = 2;

s.waitForBoot {
~dirt = SuperDirt(4, s); // pan across four channels
~dirt.loadSoundFiles;
~dirt.start(57120, 0 ! 12); // start superdirt, listening on port 57120, create twelve orbits each sending audio to channel 0
};
s.latency = 0.3;
);
s.record(numChannels:4); // output channels again
s.stopRecording;
```

## So you want your own samples...
```SuperCollider
(
s.options.numBuffers = 1024 * 256;
s.options.memSize = 8192 * 32;
s.options.maxNodes = 1024 * 32;
s.options.numOutputBusChannels = 2; // total number of output channels
s.options.numInputBusChannels = 2;

s.waitForBoot {
    ~dirt = SuperDirt(2, s); // total number of output channels
	  ~dirt.loadSoundFiles;
    ~dirt.loadSoundFiles("/Users/rrome/Documents/GitHub/solo/Dirt/samples/**"); // specify sample folder to load THIS IS THE RACHEL PATH
    s.sync; // wait for supercollider to finish booting up
    ~dirt.start(57120, 0 ! 12); // start superdirt, listening on port 57120, create twelve orbits each sending audio to channel 0
};
);
```

## N vs Note For Real
- You can never mix "note" and "n" within a single orbit
- With Samples, n meant iNdex, so it was which sample from the index you wanted to play
- With Samples, note meant: take this one sample but slow/speed it up to pitch it down and up and play the pitches as notes
- Now, with Synths: note and n mean the same thing, but you still can't mix them within a single orbit BUT pitch names == scale degree and ARE interchangeable, e.g.
`d3 $ n "0 2 e 6 0 b 6 8"
  # s "cyclo"`

## [SuperDirt Synths!](https://tidalcycles.org/docs/reference/synthesizers)
- Additive. SuperGong.
```
d1 $ n "0 2 4 6 0 2 6 8"
  # s "supergong"
  # voice sine -- 'tone' knob
  # decay sine -- harmonics decay
  # accelerate sine -- pitch glide
```
- Subtractive. SuperChip.
```
d2 $ n "0 2 4 6 0 2 6 8"
  # s "superchip"
  # slide sine -- linear pitch glide
  # rate sine -- repeats the above glide “n” times (can be fractional or negative)
  # accelerate sine -- 'overall' glid
  # pitch2 sine -- control the ratio of harmonics
  # pitch3 sine -- control the ratio of harmonics
  # voice sine -- causes variations in the levels of the 3 oscillators
```
- Subtractive. SuperReese.
```
d3 $ n "0 2 4 6 0 2 6 8"
  # s "superreese"
  # accelerate sine -- 'overall' glid
  # voice sine -- causes variations in the levels of the 3 oscillators
  # detune sine -- detune amount
```
- Modeling. SuperHammond with voices:
0. bass violin 16’
1. tibia 8’
2. bassoon 8’
3. french trumpet 8’
4. string ensemble
5. Blues
6. Jazz 1
7. Full Shout
8. Bro’ Jack
9. Jazz 2
```
d4 $ n "0 2 4 6 0 2 6 8"
  # s "superhammond"
  # voice 3
```
- Rachel favs with little documentation.
```
d5 $ n "0 2 4 6 0 2 6 8"
  # s "cyclo"`
d6 $ n "0 2 4 6 0 2 6 8"
  # s "gabor"
d7 $ n "0 2 4 6 0 2 6 8"
    # s "imp"
```
## [Sending Clock](https://tidalcycles.org/docs/configuration/MIDIOSC/midi/#synchronising-midi-clock)
  - yeah, yeah, yeah I know you'll want to use it through Live...

## Patches You're Proud Of!

## Next week: Draft of your Final Project & ORCA

## Penultimate week: FINAL PROJECT DUE and run-through of Final Concert

## Final week: FINAL CONCERT!
