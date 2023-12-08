# Visuals

## Make some noise in BNO

## Show and Tell

## Hydra
- javascript-based
- estuary!
- atom package
  - (gotta install [node.js](https://nodejs.org/en/download/))
- [in-browser sandbox](https://hydra.ojack.xyz/?sketch_id=rangga_2)
- A LOT of documentation, but not organized super-well yet

### [Hydra Functions](https://hydra.ojack.xyz/functions/)

### [Hydra Examples](https://github.com/hydra-synth/hydra-examples)
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

## For next week:
  - Midterm Presentation Proposal
    - .md from your repo into canvas
    - 10 min. presentation on a livecoding topic or work of your choice (with instructor preapproval)
- Documentation for submission: .md bibliography using MLA format
    - Be SPECIFIC! one artist, one coding language/tool, one city's algorave scene, one technique, analysis of one particular work
    - [Recommend starting here!](https://toplap.org/)
