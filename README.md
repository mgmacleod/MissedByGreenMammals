# Kasina


Extensions for Bitwig Studio that try to look deeply into what makes a piece of gear great and then bring something of that to the Bitwig world. So far, the Elektron Octatrack is the only one that I've added to this project, but there are plans for more extensions in the future.


***NOTE: This is a personal project and very much a work in progress. I hope it might be useful to others, but the intention isn't to create a general purpose extension that meets everyone's needs. That said, comments and suggestions are welcome. Create a issue if you have an idea or run into an problem.*** 

## Compatibility 

- Bitwig Studio 5.0+ 
- Should work anywhere Bitwig runs
  - At one time or another, I have tested it on Windows, MacOS, and Linux 
  - I currently develop and use it on the Mac

## Setup

### Install the extension

1. Download the latest version from the [Releases section](https://github.com/mgmacleod/Kasina/releases) of this repository and unzip it somewhere on your computer. You'll find the following inside:
   1. `accessories` folder
      1. basic template projects for Bitwig and the Octatrack that you can use to get started
   2. `Kasina.bwextension` file
   3. `LICENCE` file 
2. [Install](https://www.bitwig.com/support/technical_support/how-do-i-add-a-controller-extension-or-script-17/) the `Kasina.bwextension` file 
   1. Basically, either copy it into your extensions folder or (apparently) drag-and-drop it onto the Bitwig Studio window
3. Configure the Octatrack controller in Bitwig
   1. Open Bitwig and go to Settings > Controllers 
   2. Click '+ Add Controller'
      1. Hardware Vendor: select `Elektron`
      2. Product: select `Octatrack`
   3. Use the dropdown menus to select your MIDI input and output ports for the Octatrack

### Setup your Octatrack

1. Unzip the provided `KASINA_TEMPLATE1_OctatractProject.zip` file and load the project onto the Octatrack in USB mode
2. Open the `KASINA_TEMPLATE1` project on the Octatrack
   1. The audio side of the project is set to the defaults (all static machines, no samples loaded, etc.); set this up as you see fit
   2. The MIDI side is configured with the requirements for the extension
      1. Mainly, that means the tracks are set to use MIDI channels 9 through 16 and the CCs in Ctrl1 and Ctrl2 are set to defaults
      2. The extension also receives NOTE-ON events from the chromatic trig keys to control events in Bitwig, so make sure you set the trig keys to chromatic mode (FUNC + Down)
         1. Note also that the chromatic keyboard must be on octave 3 for this to work; if not, set it there using FUNC + Left/Right arrows, as appropriate
         2. ***This of course means you can't use the MIDI tracks for sequencing anything else, like external synths or VSTs***, but it's assumed that you're not doing that if you're interested in this extension ;)

### Setup Bitwig

1. Open Bitwig and load the provided `OT_Scene_Setup.bwproject` project 
   1. 

# Devices

## Elektron Octatrack 

![Alt text](/images/ot-layout.png?raw=true "Octatrack Layout")

This extension uses the MIDI side of the Octatrack to turn it into a powerful controller for Bitwig Studio. It provides most the basic functionality you'd expect from a MIDI controller, but also adds some extra features to integrate with Bitwig Studio.


### Features
- Control basic transport functions (Arranger only for now)
  - play
  - stop
  - record
- Adjust basic mix parameters of tracks in Bitwig Studio
  - Volume
  - Pan
  - Send 1 
  - Send 2
  - Select 
  - Arm
  - Solo
  - Mute
  - track types
    - tracks 1 - 7 on the Octatrack control regular (audio/midi/hybrid) tracks in Bitwig Studio
    - track 8 on the Octatrack controls Bitwig's master track and the project remote controls
  - trig buttons move the bank of 7 regular tracks around the project
- Adjust remote controls on tracks and devices
  - Navigate pages of remotes with trig buttons
  - trig keys toggle between track and device modes
    - in device mode, an additional set of trig keys scroll through the devices on the track
- Advanced features
  - OT scenes integration
    - Optional integration of the Octatrack's scenes into Bitwig's modulation system
      - Use modulators in Bitwig to assign parameters from native and plugin devices to the scenes of the Octatrack
      - This leverages the project-level modulators of Bitwig 5 and their ability to accept a dedicated stream of MIDI data from the OT crossfader and scene keys


https://www.bitwig.com/support/technical_support/how-do-i-add-a-controller-extension-or-script-17/

