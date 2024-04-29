# Tidal Cycles

## [Structure of Tidal Cycles](https://tidalcycles.org/docs/getting-started/tidal_start)

## SuperCollider
- Audio Engine is now SuperCollider
- Yes, still running samples, but may also control synths!
- You may now also send out clock information! (but not receive it, sorry)

## Tidal Cycles Dependencies
- [Follow the **Automatic Installation (script)** instructions here](https://tidalcycles.org/docs/getting-started/macos_install)
  - Please let me know if this doesn't work!!!

## Starting Tidal Cycles
    - select your preferred audio output device in AudioMidi Setup
    - open SuperCollider
    - execute `SuperDirt.start;` with shift, return
    - does your preferred audio output device get listed?
    - Are they the same sample rate?
    - does it say `SuperDirt: listening to Tidal on port 57120`? (this will take a moment)
    - open and save a .tidal file in Pulsar
    - execute TidalCycles code with shift, return in Pulsar
    - monitor in Pulsar and SuperCollider post windows
    - (did you already know a little sc? SuperDirt the quark boots sc itself, so please don't boot before using the quark)

## The Structure
`d1 $ n "0 2 4 6 0 2 6 8" # sound "cyclo"`

## SETTING UP PULSAR WITH HYDRA & TIDALCYCLES!
