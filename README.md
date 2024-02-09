Open FM - FM Plugin Synth
=======================

Open FM is a fork of Dexed.  
Under the hood it uses [music-synthesizer-for-android](https://github.com/google/music-synthesizer-for-android) 
for the synth engine and [JUCE](https://www.juce.com) as an application/plugin wrapper.

As time goes on the plan is to add more features not found in Dexed and remove features related to the DX 7 

Open FM is licensed on the GPL v3. The msfa component (acronym for music synthesizer for android, see msfa 
in the source folder) stays on the Apache 2.0 license to able to collaborate between projects.

Changelog
---------
#### Version 0.0.1
* Forked [Dexed](https://github.com/asb2m10/dexed/)
* Updated readme
* Added octave up and down keys

Credits & thanks
----------------
* Dexed : Pascal Gauthier and the [Dexed](https://github.com/asb2m10/dexed/graphs/contributors) team
* DX Synth engine : Raph Levien and the [msfa](https://github.com/google/music-synthesizer-for-android) team 
* [Surge Synth Team](https://surge-synth-team.org/) for substantial contributions like microtuning and MPE support.
* Graphical design : AZur Studio
* [Sentinel77](https://github.com/Sentinel77) for numerous engine fixes
* LP Filter : Filatov Vadim (2DaT); taken from the excellent [Obxd](https://obxd.wordpress.com) project
* PPPlay : Great [OPL3](https://github.com/stohrendorf/ppplay) implementation, with documented code :D
* DX7 program compilation : Jean-Marc Desprez (author of [SynprezFM](http://www.synprez.com/SynprezFM)) 
* DX7 programs : Dave Benson, Frank Carvalho, Tim Conrardy, Jack Deckard, Chris Dodunski, Tim Garrett, Hitaye, Stephan Ibsen, Christian Jezreel, Narfman, Godric Wilkie
* falkTX [distrho](http://distrho.sourceforge.net/)

TODO - Open FM
------------
* Refactor oscillator code
* Create new patch format
* Create new graphics for UI
* Update cmake files
TODO - Dexed 
------------
* Various code cleanup
* Yamaha 4 operators (DX21/DX27/DX100) sysex import

TODO - msfa
-----------
* Portamento implementation
* Better Amplitude Modulation
* Accurate live operator level envelope updates

# How to build

Clone Dexed from github

```
~ $ git clone https://github.com/quirkylemon/Open-FM.git
```

Dexed has several submodules it now depends on, including VST3/CLAP and a library to support non standard tuning. After you clone your first step is

```
~ $ cd Open-FM
~/Open-FM $ git submodule update --init --recursive
```

Then you crate the cmake build files that are will be created in the build directory. On that build you can trigger your favorite IDE or simply use `--build` cmake option.

```
~/Open-FM $ mkdir build
~/Open-FM $ cd build
~/Open-FM/build $ cmake .. -DJUCE_COPY_PLUGIN_AFTER_BUILD=TRUE
~/Open-FM/build $ cmake --build .
```

If you get missing header compilation errors, be sure to check the [known Linux dependencies](https://github.com/asb2m10/dexed/wiki/Linux-builds-dependencies) based on your distribution for Linux.

Binaries will be found in `~/Open-FM/build/Source/Open-FM_artefacts/*`
