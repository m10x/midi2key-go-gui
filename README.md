# midi2key-ng
[![Release](https://img.shields.io/github/release/m10x/midi2key-ng.svg?color=brightgreen)](https://github.com/m10x/midi2key-ng/releases/latest)
[![Go Report Card](https://goreportcard.com/badge/github.com/m10x/midi2key-ng)](https://goreportcard.com/report/github.com/m10x/midi2key-ng)
[![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/m10x/midi2key-ng)](https://golang.org/)
[![Fyne.io](https://img.shields.io/badge/Fyne-v2-blue)](https://fyne.io/)
[![Gomidi](https://img.shields.io/badge/Gomidi-v2-blue)](https://gitlab.com/gomidi/midi/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)

## About

GUI to Map Buttons, Knobs and Sliders of your Midi Controller to Different Functions. Developed for Linux (Gnome Wayland & Pop!_OS x11) and a Behringer X Touch Mini; however it should work for other Midi Controller and Distros, too!

## Features
Give your midicontroller the ability to:
- emulate key presses, mouse clicks/movements
  - Look [here](https://git.sr.ht/~geb/dotool/tree/master/doc/dotool.1.scd#L62) for possible input emulations
- write text
- run console commands
- soundboard
  - play audio files (e.g. wav, flac, ogg) as microphone input
  - new source soundboard_mic combines the default microphone with a new audio sink soundboard_router by utilizing pactl
  - run `paplay --list-file-formats` to list all available formats
- control your audio
  - input/output devices, applications, focused application (x11 and only wayland if Gnome)
  - increase/decrease/set volume
  - mute/unmute/toggle

## Screenshots
Overview of Assignments
![image](https://user-images.githubusercontent.com/4344935/199974889-86d36ddc-32c7-48cc-b986-65a83aa575a3.png)

New Assignment
![image](https://user-images.githubusercontent.com/4344935/199975309-8205d9cf-65dd-4c01-b717-c5ccb2826150.png)

Edit an Assignment
![image](https://user-images.githubusercontent.com/4344935/199975097-e79b21e4-bd12-433b-9003-53939384a237.png)

## How to Install

### Option 1: Download precompiled binary
Download a precompiled binary from the [latest Release](https://github.com/m10x/midi2key-ng/releases).  

### Option 2: Install using go
The repository can be fetched and installed using Go.  
`go install -v github.com/m10x/midi2key-ng@latest`

### Requirements

## general
- Install [DoTool](https://sr.ht/~geb/dotool/) for input emulation
    - `git clone https://git.sr.ht/\~geb/dotool` 
    - `sudo apt install scdoc`
    - `cd dotool && ./build.sh && sudo ./build.sh install`
    - `sudo udevadm control --reload && sudo udevadm trigger`
    - restart OS
    - `echo write test | dotool` to check if dotool works

## x11
- `apt install xprop xdotool` for audio control of focused application

## Wayland
- Install Gnome Extension [Window Calls Extended](https://github.com/hseliger/window-calls-extended) to control audio of focused application
  
## Roadmap
- improve log speed `log.SetOutput(multiWriter)`
- sort table https://fynelabs.com/2023/10/05/user-data-sorting-with-a-fyne-table-widget/
- soundfile picker
- spam actions if key keeps getting pressed (hold)
- multiple profiles
- hotkeys to start/stop listening
- error output in gui
- add code comments
- create default Key Mapping for Behringer X Touch Mini with an easy option to add more defaults
- export (aka Backup) / import Key Mapping
- improve design, layout etc.
- test other midi controllers

## Credits

### Frontend Framework:  
**fyne**  
https://fyne.io/

### MIDI Library:
**gomidi**  
https://gitlab.com/gomidi/midi/ 
https://pkg.go.dev/gitlab.com/gomidi/midi/v2

### Input Emulation:
**dotool**  
https://sr.ht/~geb/dotool/
