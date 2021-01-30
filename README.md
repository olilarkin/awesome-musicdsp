# More Awesome Music DSP*

This is a curated list of my favourite music DSP and audio programming resources. This was originally meant to be an official "Awesome list", but apparently you are not meant to write in the first person, so this is now a "more awesome" list.

Oli Larkin

## Frameworks
- [iPlug2](https://github.com/iPlug2) - iPlug (originally created by Cockos) is an awesome plug-in framework. I was maintaining a fork of it since ~2011 called [WDL-OL](https://github.com/olilarkin/wdl-ol) which is now superseeded by [iPlug2](https://github.com/iPlug2). In 2018 [Alex Harker](https://github.com/AlexHarker) and I made a big effort to update it and continue to work on it. iPlug's syntax is super simple, for example, creating a parameter or a control in the UI is only a single line of C++ code.
- [JUCE](https://github.com/juce-framework/JUCE) - JUCE is an undeniably awesome C++ application/plug-in framework with audio roots. It boasts a vast amount of functionality for the development of music software, including support for almost all plug-in formats and platforms. JUCE is used widely in the music technology industry and it has excellent documentation, code standards, features and support. The JUCE team organise the [Audio Developer's Conference (ADC)](https://juce.com/adc) which is the most awesome conference around if you like audio programming. What's more all the videos from all the ADCs so far are available [on youtube](https://www.youtube.com/channel/UCaF6fKdDrSmPDmiZcl9KLnQ/videos).
- [VSTGUI](https://github.com/steinbergmedia/vstgui) - VSTGUI is Steinberg's cross-platform UI toolkit for audio plug-ins. It is released under a BSD licence, it's an impressive piece of work and many plug-in developers use it for their products.
- [AudioKit](http://audiokit.io/) - Well, i'm going to break the rules and include AudioKit here which uses the Swift programming language, because if you want to make apps for Apple's devices this is a great option, although if you want to do low level stuff, you will still have to delve into C/C++. It's a DSP and UI toolkit for audio things, so going in this category. The AudioKit team have also published a nice [AUv3 template project](https://github.com/AudioKit/AUv3-Example-App).
- [WDL](https://github.com/justinfrankel/WDL) - WDL is Cockos' library of reusable C++ code, that is used to power the DAW Reaper, amongst other things. Whilst not traditionally a framework, there is so much good stuff in here, it is highly recommended - although there is next to no documentation, so it's not for the faint hearted. For more info about the various parts of WDL (which can be used independently), check [the Cockos site](https://www.cockos.com/wdl/)
- [ASPiK](http://www.aspikplugins.com/) - This is a new framework from Will Pirkle (to accompany his books) which is based on the VST3 SDK and it's AU/AAX wrappers, along with VST GUI and its runtime UI editor. It includes a project creator and a lot of extra "nuts and bolts" code for plug-in development.
- [DPF](https://github.com/DISTRHO/DPF) - Distrho Plug-in Framework is a nice C++ plug-in framework by falkTX, supporting lots of Linux formats.
- [Jamba](https://jamba.dev/) - A new framework built on top of the VST3SDK & VSTGUI, with some useful extra widgets and good CMake support
- [DPlug](https://dplug.org/) - A plug-in framework using the D programming language, that has had a huge amount of work over many years. I haven't tried it myself, but I've decided to include it here in solidarity with the authors. As a fellow open-source framework Dev, it's nice if people know about your work!

## DSP Libraries

- [Gamma](https://github.com/LancePutnam/Gamma) - Gamma is a very awesome C++ DSP framework by Lance Putnam - a developer whose name I've known since the synthedit days. The beauty of Gamma is the conciseness of the implementation of certain techniques. The STFT is a bit of a pain to code yourself, involving overlapping FFT windows etc - how about [this](https://github.com/LancePutnam/Gamma/blob/master/examples/spectral/STFT.cpp) for a concise end user implementation.
- [Q](https://github.com/cycfi/Q) - A very nice looking modern C++ DSP library with concise examples

- [HIIR](http://ldesoras.free.fr/prod.html) - HIIR is a seriously cool oversampling library by Laurent de Soras. Oversampling is something we often need in audio DSP, and this library handles it elegantly - providing a variety of classes for low latency IIR half band filtering (including SIMD optimizations). Originally this had a LGPL licence but now it's available under the [WTFPL](http://www.wtfpl.net/) - my favourite licence.
- [HOALibrary](https://github.com/CICM/HoaLibrary-Light) - A flexible DSP library for high order ambisonics (HOA) - a spatial audio platform that is becoming more and more relevant thanks to VR (GPL Licence).
- [HISSTools Library](https://github.com/AlexHarker/HISSTools_Library) - a nice BSD licensed library by Alex Harker, including FFT abstractions and multi-channel  convolution, amongst other things
- [Spatial Audio Framework](https://github.com/leomccormack/Spatial_Audio_Framework) - Another excellent library for ambisonics and other spatial audio related processing
- [MadronaLib](https://github.com/madronalabs/madronalib) - Randy Jones' DSP library, which is awesome because it is all designed for SIMD processing.

## Domain Specific Languages (DSLs)

- [FAUST](https://github.com/grame-cncm/faust) - FAUST is a powerful functional DSL for audio DSP with many options for quickly compiling to different “architectures” including audio plug-ins and embedded devices. FAUST is not interpreted like programming languages such as Puredata/Max/Supercollider/javascript, it is compiled to C++ and various other programming languages or bytecode formats such as Web Assembly (WASM). This functionality is suited to rapid prototyping but can also produce robust and performant binaries. Whilst the rapid prototyping possibilities of FAUST are appealing to me, what I like most about it is the extensive library of high quality DSP, particularly for physical modelling synthesis and the way in which you can compose algorithms using the consise syntax. FAUST includes a JIT compiler "libfaust" based on LLVM, which I [integrated into a JUCE module](https://github.com/olilarkin/juce_faustllvm). I've also [integrated FAUST support into iPlug2](https://github.com/iPlug2/iPlug2/tree/master/Examples/IPlugFaustDSP) and used it to make a [physical model of the Indian Tambura](https://github.com/olilarkin/tambura).
- [SOUL](https://soul.dev) - Is an exciting new DSL created by Jules Storer and Cesare Ferrari at Roli, which also uses the LLVM compiler technology (see [ADC18 Keynote](https://www.youtube.com/watch?v=-GhleKNaPdk)). It has a JIT compiler for a fast workflow and can spit out C++ and WASM and ready-to-go JUCE projects. The language has been designed with the goal of allowing the audio DSP to run "closer to the metal" in a similar way that GPU shader languages such as GLSL can run securely on graphics hardware. SOUL is an imperative language much more similar to C/C++/Javascript than FAUST. It has several advantages, for example multi-rate processing and in my opinion it is more suited for code that mixes event-handling with DSP, where as FAUST is good for discreet blocks of DSP processing. Since FAUST can output SOUL code via [faust2soul](https://www.youtube.com/watch?v=GPygBgyEANs), you can use them together! [Here](https://github.com/olilarkin/SOULReplicant) is a SOUL thing I did.

## DSP Filters

- [Filter Playground](https://smus.com/filter-playground) - A nice blog post and [web audio tool](https://borismus.github.io/filter-playground/) demonstrating IIR filters
- [MicroModeler Filter Design Tool](https://www.micromodeler.com) - An excellent web based filter design tool
- [DSPFilters](https://github.com/vinniefalco/DSPFilters) - Vinno Falco made this excellent MIT licensed IIR filter library. [Here](https://github.com/olilarkin/DSPFilters) is a fork to work with the latest JUCE. See also [iir1](https://github.com/berndporr/iir1), which seems a futher developed and improved version.

## Reading
This is a small selection of books that have been helpful to me. There are many others that look absolutely great but I have not used them in anger (yet).

- [Will Pirkle](http://www.willpirkle.com/) - Will Pirkle has written two books that will be invaluable the aspiring audio plug-in developer - "Designing Audio Effect Plug-Ins in C++" and "Designing Software Synthesizer Plug-Ins in C++". The books contain detailed information about important audio DSP, including modern virtual analogue techniques, and sample code for complete sythesizers that sound good. My only criticism is that a large part of the books relates to a bespoke plugin framework and providing information for multiple formats, AU, VST3 can be a bit overwhelming, and clutters the content. Nevertheless I highly recommend these books. For more info [see here](http://www.willpirkle.com/about/books)
- [Dodge and Jerse - Computer Music: Synthesis, Composition and Performance, 2nd Edition](https://books.google.co.uk/books/about/Computer_Music.html?id=eY_BQgAACAAJ&redir_esc=y) - This is my absolute favourite book to recommend to students studying computer music/audio synthesis. I find the book does not date like some other computer music texts. The MUSIC-N style block diagrams are charming and the techniques are discussed very well.
- [Udo Zölzer (Ed) - DAFX: Digital Audio Effects](https://books.google.co.uk/books/about/DAFX.html?id=DX-mRhkJL74C&source=kp_cover&redir_esc=y) - This is a great book on audio DSP, written by a variety of domain experts, and it includes Matlab code examples.
- [JOS](https://ccrma.stanford.edu/~jos/) - Julius Smith's site and his four books are an amazing resource. Matlab and FAUST code examples included!
- [DAFX Conference Archive](http://www.dafx.de/) - All the papers from the DAFX conference are available online. Another great resource.
- [EarLevel Engineering](http://www.earlevel.com/) - Nigel Redmond's DSP blog contains some very nicely written explanations of a variety of topics.
- [Michael Tyson blog](http://atastypixel.com/blog/four-common-mistakes-in-audio-development/) - In depth article about Four common mistakes in audio development
- [Ross Bencina's blog/site](http://www.rossbencina.com/) - Another Australian who writes a lot of interesting software and articles about lock free programming

## Tools
Slightly veering off topic, these are the software tools that I find useful in my audio programming. Xcode and Visual Studio Community are the free IDEs that I use, and both are very powerful these days.

- [Cycling '74 Max](https://cycling74.com/) - Max is a great environment to use for prototyping audio plug-ins. There are just so many options for integrating different technologies, I highly recommend it - even if nowadays most of the max patches I make only include a few objects!
- [Desmos](https://www.desmos.com) - This is an awesome online graphing calculator. Check out some interactive Casio CZ waveforms that I made [saw](https://www.desmos.com/calculator/te4bzpvav3) [square](https://www.desmos.com/calculator/mclynvox0h) [reso1](https://www.desmos.com/calculator/6659cif7oa)
- [Coliru](http://coliru.stacked-crooked.com/) - This is an online interactive C++ compiler, which can be a very nice and quick way to test out a particular feature of the language, without having to build a binary.
- [Compiler Explorer](https://godbolt.org/) - Compiler explorer is a great tool for checking the assembly code that different compilers will produce.
- [FAUST Web IDE](https://faustide.grame.fr/) - This is an online FAUST IDE and compiler, that lets you test FAUST code with webaudio. You can then tell it to output a zip file with a binary for your preferred platform. This saves you all the trouble of installing FAUST and its dependencies on your local machine.
- [SOUL Web IDE](https://soul.dev/lab/) - Compile and run SOUL code in the browser
- [Matplotlib-cpp](https://github.com/lava/matplotlib-cpp) - A C++ interface to the matplotlib python plotting tool. Allows you to visualize algorithms using the same code that you can use in production.
- [xeus-cling](https://mybinder.org/v2/gh/QuantStack/xeus-cling/stable?filepath=notebooks/xcpp.ipynb) - This is a really cool project allowing you to use JIT compiled C++ in jupyter notebooks - which, like Matplotlib-cpp above is great for visualizing algorithms using the same code that you can use in production, inside the popular jupyter notebook format. [Here](https://github.com/olilarkin/XeusClingMatplotLibExample) is an example of how you can use those things together, easily via a ready made docker image.
- [StudioRack plugin manager](https://studiorack.github.io/studiorack-site/) - Open-source audio plugin manager tool and Github plugin templates to automatically build cross-platform audio plugins.

## Misc open source audio code/projects
I got into programming in C/C++ by making objects for Max and Synthedit. Learning how to use the SDKs for one of those or for one of the following open source packages is a nice way to start in my opinion, since you don't need to think about too many things. What's more - these great projects all show you how you can go about certain tasks... the code is there for you to look at. It might take you a while to find it, and sometimes the code might be hard to understand, but they all have oscillators, filters etc. There are many third party objects as well, that are also open source. 

- [puredata](http://msp.ucsd.edu/software.html) - I don't think pd needs an introduction! Also check out [libpd](https://github.com/libpd), which you can use as an embeddable DSP runtime in your C++ audio plug-in etc.
- [supercollider](https://github.com/supercollider/supercollider) - Likewise, but make sure you look at the scsynth part for DSP stuff.
- [csound](https://github.com/csound/csound) - CSound has seen a renaisannce of late and can be used as an embedable DSP library
- [vcvrack](https://github.com/VCVRack/Rack) - Whilst the other items in this list have been around a while and have somewhat arcane code-bases, this is pretty new and the API is very clean and simple. I think making a VCVRack module it is a great way to get into audio programming.
- [tracktion engine](https://github.com/Tracktion/tracktion_engine) - Source code for an entire DAW engine, using modern C++. An amazing resource for learning all sorts of things including how to structure and architect large audio projects. GPL/Commercial license.
- [musicdsp.org](https://www.musicdsp.org) - "A collection of algorithms, thoughts and snippets, gathered for the music dsp community". A long serving site that has recently been revamped. Beware: most of the code there was written a very long time ago, and optimization tricks etc, may not be relevant on modern machines. Also there are lots of code snippets programming languages other than C++ (delphi, java, C#  etc). Could do with some curation.
- [Webkit's Web Audio API](https://github.com/WebKit/WebKit/tree/main/Source/WebCore/Modules/webaudio) - This is the C++ code for WebKit's implementation of the Web Audio API, as used in Safari.
- [Blink's Web Audio API](https://chromium.googlesource.com/chromium/blink/+/master/Source/modules/webaudio/) - The same thing in Blink (Google chromium).
- [Firefox's Web Audio API](https://searchfox.org/mozilla-central/source/dom/media/webaudio/) - And for Mozilla Firefox!

## Open source instruments/effects
Here are some quality open source instruments/effects plug-in projects.
- [surge](https://github.com/surge-synthesizer/surge) - Surge was an excellent product from a very talented developer and it's recently been open sourced and updated to work with modern versions of VSTGUI.
- [helm](https://github.com/mtytel/helm) - Helm is a comprehensive synth with a modern user interface written with JUCE, using OpenGL for visualisation widgets.
- [obxd](https://github.com/2DaT/Obxd) - OBxd  is a great sounding oberheim emulation, written with JUCE. [DiscoDSP have updated it](https://github.com/reales/OB-Xd), and it has also been [ported to work on the web as a WebAudioModule](http://www.webaudiomodules.org/wamsynths/obxd)
- [dexed](https://github.com/asb2m10/dexed) - Dexed is a JUCE frontend to [Raph Levien's "Music Synthesier For Android"](https://github.com/google/music-synthesizer-for-android), which is an excellent DX7 emulation. Also [ported to work on the web as a WebAudioModule](http://www.webaudiomodules.org/wamsynths/dexed)
- [AudioKit SynthOne](https://github.com/AudioKit/AudioKitSynthOne) - SynthOne is a great open source project built using Audiokit,  that will be very interesting to anyone looking to build an iOS synthesiser.
- [AirWindows Plugins](https://github.com/airwindows/airwindows) - A large collection of GUI-less plug-ins open source but supported via patreon [see airwindows site](http://www.airwindows.com/)
- [Temper](https://github.com/creativeintent/temper) - A digital distortion built using JUCE and FAUST
- [mutable instruments](https://github.com/pichenettes/eurorack) - Emilie Gillet's work is very inspiring. Although written for microcontrollers, there is so much to learn from here. And it's [ported to VCVRack](https://github.com/VCVRack/AudibleInstruments/tree/master/src) so you can try it on the desktop.
- [zita stuff](http://kokkinizita.linuxaudio.org/linuxaudio/index.html) - Fons Adriaensen's linux audio projects offer a lot of great tools for acoustic measurements, spatial audio etc - mostly as jack apps.

## Working with hardware
Most of the audio programming that I do has to do with plug-ins, but I found a couple of hardware platforms that I really like developing for (mainly because writing code for these devices is not so different to making a plug-in).

- [the owl pedal/module](https://hoxtonowl.com/) - This is a programmable stomp box and eurorack module that I've been working with since the kick starter campaign to launch it. It's a really nice little unit, which you can program in C++, FAUST, Pd or with Max gen~. I find the limited interface with 4 controls makes me think quite carefully about what's important about my DSP algorithm. You can find some patches I made for it (using a mixture of c++ and FAUST) in the [user library](https://www.rebeltech.org/patch-library/patches/authors), and the original code [here](https://github.com/olilarkin/OL-OWLPatches).
- [bela](https://bela.io/) - Bela is a wonderful little SoC + Audio Interface which is pretty revolutionary, allowing super low latency audio and sensor I/O all clocked together, in a tiny package. I wrote the FAUST support class for bela. You can also program it with C++ or libpd, and even supercollider.
- [ELK Audio OS](https://elk.audio/dev-kit/) - A new embedded linux OS & dev kit that runs VST2 & VST3 plugins.

## Youtubers / Stuff to watch

- [TheAudioProgrammer](https://www.youtube.com/channel/UCpKb02FsH4WH4X_2xhIoJ1A) - includes a lot of tutorials about JUCE with guest slots on things like web audio.
- [TheChernoProject](https://www.youtube.com/user/TheChernoProject) - although this channel is focused on game development, the [C++ series](https://www.youtube.com/watch?v=18c3MTX0PK0&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb) is excellent. Highly recommended.
- [Teaching Yourself to Make Music Software: Steve Duda in Conversation | Loop](https://www.youtube.com/watch?v=Cp0rtLaXBio&t=1456s) - an inspiring interview with a great developer about a killer synth.
- [Sean Costello (Valhalla DSP) on reverb design](https://youtu.be/aJLhqfHrwsw) - great talk by another great plugin developer
- [C++ Real-Time Audio Programming with Bela](https://www.youtube.com/playlist?list=PLCrgFeG6pwQmdbB6l3ehC8oBBZbatVoz3) - A very clearly presented course.
- [Vadim Zavalishin - The Art of VA Filter Design, ADC 2018](https://www.youtube.com/watch?v=zPzCLqkQnr0) - Video overview of [the book](https://www.native-instruments.com/fileadmin/ni_media/downloads/pdf/VAFilterDesign_2.1.0.pdf)
- [HOW MOOG MAKES SYNTH APPS: INTERVIEW WITH GEERT BEVIN, HEAD OF SOFTWARE AT MOOG](https://audiokitpro.com/geert-moog/) - great interview full of insight

## Places
Here are a few links to the various corners of the internet and real-world where you might like to hang out if you like this kind of stuff...

- [musicdsp mailing list](http://sites.music.columbia.edu/cmc/music-dsp/) - The music DSP mailing list is pretty quiet these days, but it still worth signing up, despite the web 0-1 front page. Every now and again a music DSP legend posts something interesting. 
- [KvR Audio DSP and Plug-in Development Forum](https://www.kvraudio.com/forum/viewforum.php?f=33) - This is probably the most active forum for audio DSP that is not aligned with a particular plug-in framework. There are some very smart people, some mavericks and some plain weirdos who hang out here.
- [JUCE Forums](https://forum.juce.com/) - This is a collection of forums centred around the variety of things that JUCE does. Since there is such a huge amount of people using JUCE to make audio software, there is a lot of good info here.
- [Cockos Forums](https://forum.cockos.com) - Another collection of forums centred around Cockos' tools including one for WDL/iPlug and one for Reaper JS.
- [The audio developer conference (ADC)](https://juce.com/adc) - Whilst the other places mentioned here are all virtual, this is a real conference where you can go and meet real people face-to-face who do audio programming - highly recommended!
- [TheAudioProgrammer Discord server](https://www.youtube.com/watch?v=E3KOptgChdc) - A popular community for discussing audio programming.
- [iPlug2 Forum](https://iplug2.discourse.group/) - new forum for iPlug2 discussions

___

Oli Larkin 2018-2020
www.olilarkin.co.uk

## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
