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
## [Sending Clock](https://tidalcycles.org/docs/configuration/MIDIOSC/midi/#synchronising-midi-clock)

## N vs Note For Real
- You can never mix "note" and "n" within a single orbit
- With Samples, n meant iNdex, so it was which sample from the index you wanted to play
- With Samples, note meant: take this one sample but slow/speed it up to pitch it down and up and play the pitches as notes
- Now, with Synths: note and n mean the same thing, but you still can't mix them within a single orbit BUT pitch names == scale degree and ARE interchangeable, e.g.
`d3 $ n "0 2 e 6 0 b 6 8"
  # s "cyclo"`
