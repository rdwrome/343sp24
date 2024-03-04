# Visuals

<!--- ## Make some noise in BNO

## Show and Tell --->

## Hydra
- javascript-based
- estuary!
- [in-browser sandbox](https://hydra.ojack.xyz/?sketch_id=example_3)
- A LOT of GREAT documentation, but not organized super-well yet
- [the discord server is great!](https://discord.com/invite/ZQjfHkNHXC)

### [using the sandbox]
- shuffle patch
- shuffle parameter
- reload
- s0 vs. o0
- everybody now!

### [Hydra Functions](https://hydra.ojack.xyz/functions/)
- [osc](https://hydra.ojack.xyz/docs/docs/learning/video-synth-basics/src/)
- shape
- gradient
- all geometry
- [src/external sources](https://hydra.ojack.xyz/docs/docs/learning/video-synth-basics/external-sources/)
- [modulate](https://hydra.ojack.xyz/docs/docs/learning/video-synth-basics/combinecoord/)
- [arrays](https://hydra.ojack.xyz/docs/docs/learning/sequencing-and-interactivity/arrays/)
- [multiple outputs](https://hydra.ojack.xyz/docs/docs/learning/video-synth-basics/combine/)
- [mouse](https://hydra.ojack.xyz/functions/#functions/mouse/0)
- [bpm](https://hydra.ojack.xyz/functions/#functions/bpm/0)

### not now, but soon
- pulsar/atom package
  - (gotta install [node.js](https://nodejs.org/en/download/))
- [fft](https://hydra.ojack.xyz/docs/docs/learning/sequencing-and-interactivity/audio/)
- [midi](https://hydra.ojack.xyz/docs/docs/learning/sequencing-and-interactivity/midi/)
- [hydra-superdirt](https://github.com/munshkr/hydra-superdirt)

### [Hydra Garden](https://hydra.ojack.xyz/garden/)
- roll through
- play with some parameters
- show and tell

### Accessibility
- Let your musicians see the screen
- Don't give someone a seizure

## Estuary > OBS NINJA > OBS

## Virtual Audio Interfaces
- [BlackHole](https://existential.audio/blackhole/)
  - uncomplicated, unpowerful
  - Download 16ch
- JACK
  - complicated, powerful
- SoundFlower
  - deprecated, but otherwise perfect

## TidalCycles/SuperCollider Audio > BlackHole > OBS
- ORDER OF OPERATIONS CRITICAL!
- **Audio MIDI Setup**
  - [(Create Multi-Output Device)](https://github.com/ExistentialAudio/BlackHole/wiki/Multi-Output-Device)
  - Input: BlackHole 16ch
  - Output: Multi-Output Device
    - BlackHole 16ch Use box checked!
    - Your MONITOR source (external headphones, etc.) Use box checked!
- **SuperCollider**
  - Input: N/A
  - Output: BlackHole 16ch
  - If you need to change it run this then reboot server:
<pre>
  Server.default.options.outDevice_("BlackHole 16ch");
</pre>
- **OBS**
  - Main Window: Add Source to Scene
    - Audio Input Capture
      - BlackHole 16 ch

## Review of assignments and due dates for middle of semester
- **Analysis/Research Presentation March 25!**
- 7 min. presentation on a SPECIFIC livecoding topic or work of your choice (with instructor preapproval)
- Be SPECIFIC! one artist, one coding language/tool, one city's algorave scene, one technique, analysis of one particular work
- can't be Hydra or SuperCollider
- Documentation for submission: .md bibliography using [MLA format](https://owl.purdue.edu/owl/research_and_citation/mla_style/mla_formatting_and_style_guide/mla_general_format.html).
<!---
## For next week:
  - Midterm Presentation Proposal
    - .md from your repo into canvas
    - 10 min. presentation on a livecoding topic or work of your choice (with instructor preapproval)
- Documentation for submission: .md bibliography using MLA format
    - Be SPECIFIC! one artist, one coding language/tool, one city's algorave scene, one technique, analysis of one particular work
    - can't be Hydra or SuperCollider
--->
