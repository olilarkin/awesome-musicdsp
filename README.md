# More Awesome Music DSP*

This is a curated list of my favourite music DSP and audio programming resources. * It was originally meant to be an official "Awesome list", but apparently you are not meant to write in the first person, so it is now a "more awesome" list.

Oli Larkin

## Audio Plug-in/App Frameworks

- [iPlug2](https://github.com/iPlug2) - Originally created by Cockos, iPlug is an awesome plug-in framework. For a long time, I was maintaining a [fork of iPlug1](https://github.com/olilarkin/wdl-ol), but over the last few years [Alex Harker](https://github.com/AlexHarker) and I have reworked it into something new, with the imaginitive name: iPlug2. It's a massive improvement on the original version, adding support for GPU accelerated vector graphics, resizable high DPI UIs, iOS, WebViews, AUv3 and compiling to WebAudio/WASM, amongst many other things. iPlug2's syntax is super simple, for example, creating a parameter or a control in the UI is only a single line of C++ code.
- [JUCE](https://github.com/juce-framework/JUCE) - JUCE is an undeniably awesome C++ application/plug-in framework with audio roots. It boasts a vast amount of functionality for the development of music software, including support for almost all plug-in formats and platforms. JUCE is used widely in the music technology industry and it has excellent documentation, code standards, features and support. The JUCE team organise the [Audio Developer's Conference (ADC)](https://juce.com/adc) which is one of the best conferences to attend if you like audio programming. What's more all the videos from all the ADCs so far are available [on youtube](https://www.youtube.com/channel/UCaF6fKdDrSmPDmiZcl9KLnQ/videos).
- [AudioKit](http://audiokit.io/) - AudioKit uses the Swift programming language. It's a high level DSP and UI toolkit for audio things. If you want to make apps for Apple's devices this is a great option, although if you want to do more low level, custom DSP, you will still have to do some C/C++. The AudioKit team have also published a nice [AUv3 template project](https://github.com/AudioKit/AUv3-Example-App).
- [ASPiK](http://www.aspikplugins.com/) - This is a framework from [Will Pirkle](https://www.willpirkle.com/), used in his books, which is based on the VST3 SDK and it's AU/AAX wrappers, along with VST GUI and its runtime UI editor. It includes a project creator and a lot of extra "nuts and bolts" code for plug-in development.
- [DPF](https://github.com/DISTRHO/DPF) - Distrho Plug-in Framework is a nice C++ plug-in framework by falkTX, supporting lots of Linux formats.
- [Jamba](https://jamba.dev/) - A new framework built on top of the VST3SDK & VSTGUI, with some useful extra widgets and good CMake support
- [DPlug](https://dplug.org/) - A plug-in framework using the D programming language, that has had a huge amount of work over many years. I haven't tried it, but I've decided to include it here in solidarity with the authors. As a fellow open-source framework developer, it's nice if people know about your work.


## Exemplary open-source plug-in instruments/effects and templates
This is a new section for plug-in projects that are great examples for plug-in dev in the year 2023, where the authors are using modern practices such as CI/CD, unit-testing and have nice build scripts, and are making their projects easy for others to compile straight away!

- [pamplejuce](https://github.com/sudara/pamplejuce) - An excellent template for JUCE projects.
- [iPlug2OOS](https://github.com/iPlug2/iPlug2OOS) - Continuing the theme of self-promotion, here is the latest and greatest iPlug2 template project, set up with CI/CD, installer scripts, github workspaces etc.
- [surge](https://github.com/surge-synthesizer/surge) - Surge was an excellent product which has been open sourced and is now being maintained and continually improved by the surge-synth team, with a new JUCE UI.
- [valentine](https://github.com/Tote-Bag-Labs/valentine) - An awesome compressor and great, complete project example for a cross platform audio plug-in in 2023.
- [vital](https://github.com/mtytel/vital) - Vital is a very succesful wavetable synth with a slick interface done using the GPU. Amazing that a project like this can be open source!

## UI Frameworks

- [VSTGUI](https://github.com/steinbergmedia/vstgui) - VSTGUI is Steinberg's cross-platform UI framework for audio plug-ins. It is released under a BSD licence, it's an impressive piece of work and many plug-in developers use it for their products.
- [Elements](https://github.com/cycfi/elements) - A very promising UI framework for audio software using modern C++.
- [PUGL](https://github.com/lv2/pugl) - A cross platform GLFW-like solution that lets plug-in developers use OpenGL for their UIs

## DSP Libraries

- [Gamma](https://github.com/LancePutnam/Gamma) - Gamma is a very awesome C++ DSP library by Lance Putnam. The beauty of Gamma is the conciseness of the implementation of certain techniques. How about [this](https://github.com/LancePutnam/Gamma/blob/master/examples/spectral/STFT.cpp) for a concise STFT example.
- [Q](https://github.com/cycfi/Q) - A very nice looking modern C++ DSP library with concise examples
- [HIIR](http://ldesoras.free.fr/prod.html) - HIIR is a seriously cool oversampling library by Laurent de Soras. Oversampling is something we often need in audio DSP, and this library handles it elegantly - providing a variety of classes for low latency IIR half band filtering (including SIMD optimizations). Originally this had a LGPL licence but now it's available under the [WTFPL](http://www.wtfpl.net/) - my favourite licence.
- [HOALibrary](https://github.com/CICM/HoaLibrary-Light) - A flexible DSP library for high order ambisonics (HOA) - a spatial audio platform that is becoming more and more relevant thanks to VR (GPL Licence).
- [HISSTools Library](https://github.com/AlexHarker/HISSTools_Library) - a nice BSD licensed library by Alex Harker, including FFT abstractions and multi-channel  convolution, amongst other things
- [Mach1 Spatial SDK](https://github.com/Mach1Studios/m1-sdk) - Vector based multichannel & spatial audio APIs for customizing multichannel or spatial audio pipelines & tools and agnostically playback any spatial, surround soundfields.
- [Spatial Audio Framework](https://github.com/leomccormack/Spatial_Audio_Framework) - Another excellent library for ambisonics and other spatial audio related processing
- [MadronaLib](https://github.com/madronalabs/madronalib) - Randy Jones' DSP library, which is awesome because it is all designed for SIMD processing.
- [WDL](https://github.com/justinfrankel/WDL) - WDL is Cockos' library of reusable C++ code, that is used to make the DAW Reaper, amongst other things. It includes open source implementations of many useful things such as resampling and convolution, although there is next to no documentation and the code is difficult to understand. For more info about the various parts of WDL (which can be used independently), check [the Cockos site](https://www.cockos.com/wdl/)
- [DaisySP](https://electro-smith.github.io/DaisySP/) - A MIT licensed DSP library written for the Daisy platform, but also useable elsewhere. I like it because it includes some nice ports of Emilie Gillet's mutable instruments code.
- [SignalSmithDSP](https://signalsmith-audio.co.uk/code/dsp/) - A really nice looking DSP library, along with a really nice [blog/website](https://signalsmith-audio.co.uk/writing/) with a collection of nice articles, e.g. [How to write a reverb](https://signalsmith-audio.co.uk/writing/2021/lets-write-a-reverb/), see also [a video presentation](https://www.youtube.com/watch?v=QWnD30xHjW4)

## Domain Specific Languages (DSLs)

- [FAUST](https://github.com/grame-cncm/faust) - FAUST is a powerful functional DSL for audio DSP with many options for quickly compiling to different “architectures” including audio plug-ins and embedded devices. FAUST is not interpreted like programming languages such as Puredata/Max/Supercollider/javascript, it is ["transpiled"](https://stackoverflow.com/questions/44931479/compiling-vs-transpiling) to C++ and various other programming languages or bytecode formats such as Web Assembly (WASM). This functionality is suited to rapid prototyping but can also produce robust and performant binaries. Whilst the rapid prototyping possibilities of FAUST are appealing to me, what I like most about it is the extensive library of high quality DSP, particularly for physical modelling synthesis and the way in which you can compose algorithms using the concise syntax. FAUST includes a JIT compiler "libfaust" based on LLVM, which I [integrated into a JUCE module](https://github.com/olilarkin/juce_faustllvm). I've also [integrated FAUST support into iPlug2](https://github.com/iPlug2/iPlug2/tree/master/Examples/IPlugFaustDSP) and used it to make a [physical model of the Indian Tambura](https://github.com/olilarkin/tambura).
- [cmajor](https://github.com/SoundStacks/cmajor) - Is an exciting new DSL created by Jules Storer and Cesare Ferrari at SoundStacks, which also uses the LLVM compiler technology. It has a JIT compiler for a fast workflow and can spit out C++ and WASM and ready-to-go JUCE projects. cmajor is an imperative language much more similar to C/C++/Javascript than FAUST. It has several advantages, for example multi-rate processing and in my opinion it is more suited for code that mixes event-handling with DSP, where as FAUST is good for discreet blocks of DSP processing. Since FAUST can output cmajor code via faust2cmajor, you can use them together.

## Filter design

- [Filter Playground](https://smus.com/filter-playground) - A nice blog post and [web audio tool](https://borismus.github.io/filter-playground/) demonstrating IIR filters
- [MicroModeler Filter Design Tool](https://www.micromodeler.com) - An excellent web based filter design tool
- [DSPFilters](https://github.com/vinniefalco/DSPFilters) - Vinno Falco made this excellent MIT licensed IIR filter library. [Here](https://github.com/olilarkin/DSPFilters) is a fork to work with the latest JUCE. See also [iir1](https://github.com/berndporr/iir1), which seems a further developed and improved version.
- [RBJ Cookbook](https://webaudio.github.io/Audio-EQ-Cookbook/audio-eq-cookbook.html) - HTML version of Robert Bristow-Johnson's EQ cookbook
- [Cytomic Technical Papers](https://cytomic.com/index.php?q=technical-papers) - Andy Simper's technical papers, which include code examples and theory for modern approaches to filter design
- [Vadim Zavalishin - The Art of VA Filter Design](https://www.native-instruments.com/fileadmin/ni_media/downloads/pdf/VAFilterDesign_2.1.0.pdf) - Very math-heavy text on those modern approachs

## Reading
This is a small selection of websites, books and articles that have been helpful to me.

- [Will Pirkle](http://www.willpirkle.com/) - Will Pirkle has written two books that will be invaluable the aspiring audio plug-in developer - "Designing Audio Effect Plug-Ins in C++" and "Designing Software Synthesizer Plug-Ins in C++". The books contain detailed information about important audio DSP, including modern virtual analogue techniques, and sample code for complete sythesizers that sound good. My only criticism is that a large part of the books relates to a bespoke plugin framework and providing information for multiple formats, AU, VST3 can be a bit overwhelming, and clutters the content. Nevertheless I highly recommend these books. For more info [see here](http://www.willpirkle.com/about/books)
- [Dodge and Jerse - Computer Music: Synthesis, Composition and Performance, 2nd Edition](https://books.google.co.uk/books/about/Computer_Music.html?id=eY_BQgAACAAJ&redir_esc=y) - This is my absolute favourite book to recommend to students studying computer music/audio synthesis. I find the book does not date like some other computer music texts. The block diagrams are charming and the techniques are discussed very well.
- [Udo Zölzer (Ed) - DAFX: Digital Audio Effects](https://books.google.co.uk/books/about/DAFX.html?id=DX-mRhkJL74C&source=kp_cover&redir_esc=y) - This is a great book on audio DSP, written by a variety of domain experts, and it includes Matlab code examples.
- [JOS](https://ccrma.stanford.edu/~jos/) - Julius Smith's site and his four books are an amazing resource. Matlab/Octave and FAUST code examples included.
- [DAFX Conference Archive](http://www.dafx.de/) - All the papers from the DAFX conference are available online. Another great resource.
- [EarLevel Engineering](http://www.earlevel.com/) - Nigel Redmond's DSP blog contains some very nicely written explanations of a variety of topics.
- [Michael Tyson blog](http://atastypixel.com/blog/four-common-mistakes-in-audio-development/) - In depth article about Four common mistakes in audio development
- [Ross Bencina's blog/site](http://www.rossbencina.com/) - A developer who writes a lot of interesting software and articles about lock free programming
- [Sound on Sound Magazine Synth Secrets](https://www.soundonsound.com/series/synth-secrets) - A nice series on synthesis techniques.
- [Jatin Chowdhury @ medium](https://jatinchowdhury18.medium.com) - This blog, along with [Jatin's github](https://github.com/jatinchowdhury18) is full of fascinating, cutting-edge stuff.
- [RS-MET tutorials](http://www.rs-met.com/tutorials.html) - Some nice pdfs with clear explanations of audio DSP topics.
- [Melatonin Blog](https://melatonin.dev/blog/) - Sudara is writing some really excellent articles on some of the painful tasks involved in audio plug-in development and also publishing lots of useful open source recipes on [his github](https://github.com/sudara)
- [Katja's Home](https://www.katjaas.nl/home/home.html) - a very cool site with writings about various DSP topics and examples in pd/c

## Tools
These are the software tools that I find useful in my audio programming.

- [VSCode & Github Codespaces](https://code.visualstudio.com/) - VSCode is a brilliant text editor that has lots of interesting extensions and functionality. Lately I am using VSCode remote containers and Github Codespaces [see video](https://www.patreon.com/posts/audio-plug-in-44267675) which I think is a game-changing technology.
- [Cycling '74 Max](https://cycling74.com/) - Max is a great environment to use for prototyping audio plug-ins. There are just so many options for integrating different technologies, I highly recommend it - even if nowadays most of the max patches I make only include a few objects.
- [Desmos](https://www.desmos.com) - This is an awesome online graphing calculator. Check out some interactive Casio CZ waveforms that I made [saw](https://www.desmos.com/calculator/te4bzpvav3) [square](https://www.desmos.com/calculator/mclynvox0h) [reso1](https://www.desmos.com/calculator/6659cif7oa)
- [Coliru](http://coliru.stacked-crooked.com/) - This is an online interactive C++ compiler, which can be a very nice and quick way to test out a particular feature of the language, without having to build a binary.
- [Compiler Explorer](https://godbolt.org/) - Compiler explorer is a great tool for checking the assembly code that different compilers will produce.
- [FAUST Web IDE](https://faustide.grame.fr/) - This is an online FAUST IDE and compiler, that lets you test FAUST code with webaudio. You can then tell it to output a zip file with a binary for your preferred platform. This saves you all the trouble of installing FAUST and its dependencies on your local machine.
- [Matplotlib-cpp](https://github.com/lava/matplotlib-cpp) - A C++ interface to the matplotlib python plotting tool. Allows you to visualize algorithms using the same code that you can use in production.
- [xeus-cling](https://mybinder.org/v2/gh/QuantStack/xeus-cling/stable?filepath=notebooks/xcpp.ipynb) - This is a really cool project allowing you to use JIT compiled C++ in jupyter notebooks - which, like Matplotlib-cpp above is great for visualizing algorithms using the same code that you can use in production, inside the popular jupyter notebook format. [Here](https://github.com/olilarkin/XeusClingMatplotLibExample) is an example of how you can use those things together, easily via a ready made docker image.
- [StudioRack plugin manager](https://studiorack.github.io/studiorack-site/) - Open-source audio plugin manager tool and Github plugin templates to automatically build cross-platform audio plugins.
- [dspplot](https://github.com/kfrlib/dspplot) - A python script that I find useful for plotting filter responses
- [Docker desktop](https://www.docker.com/products/docker-desktop) - Docker is incredibly useful for creating reproducible environments, e.g. with specific python libraries installed.
- [Audio Programming Environment - APE](http://www.jthorborg.com/) - An audio plug-in that embeds a C++ JIT compiler which you can use to test your C++ DSP without leaving the DAW.
- [Fig](https://fig.io/) - Very useful macOS CLI enhancer
- [OhMyZSH](https://ohmyz.sh/) - Make macOS terminal/iTerm2 nice and colorful

## Miscellaneous open source audio code/projects

- [ni-media](https://github.com/NativeInstruments/ni-media) - A very nice audio file loading library from Native Instruments
- [choc](https://github.com/Tracktion/choc) - From the creator of JUCE comes CHOC, an ISC licensed library of Classy Header-Only Classes. Including some useful audio related utilities
- [BespokeSynth](https://github.com/BespokeSynth/BespokeSynth) - A pretty amazing modular synth/composition environment with nice real-time visualisation, loads of modules, and lots of flexibility
- [destroyfx](https://github.com/sophiapoirier/destroyfx) - A brilliant collection of open source plug-ins that are very original have been around since the dawn of VST.
- [puredata](http://msp.ucsd.edu/software.html) - Pd is a really nice cross platform dataflow programming environment. Also check out [libpd](https://github.com/libpd), which you can use as an embeddable DSP runtime in your C++ audio plug-in etc. [Camomille](https://github.com/pierreguillot/Camomile) combines libpd with JUCE to let you make plug-ins based on Pd patches.
- [supercollider](https://github.com/supercollider/supercollider) - Likewise, but make sure you look at the scsynth part for DSP stuff.
- [csound](https://github.com/csound/csound) - CSound is still going strong after many years. It can also be used as an embeddable DSP library. There is a [Web IDE](https://ide.csound.com), which is a great way to play with interesting scores/orchestras/UDOs that you find on the web and [Cabbage](https://cabbageaudio.com/) lets you make plug-ins based on CSound orchestras.
- [vcvrack](https://github.com/VCVRack/Rack) - Whilst the other items in this list have been around a while and have somewhat arcane code-bases, this is pretty new and the API is very clean and simple. I think making a VCVRack module it is a great way to get into audio programming.
- [tracktion engine](https://github.com/Tracktion/tracktion_engine) - Source code for an entire DAW engine, using modern C++. An amazing resource for learning all sorts of things including how to structure and architect large audio projects. GPL/Commercial license.
- [musicdsp.org](https://www.musicdsp.org) - "A collection of algorithms, thoughts and snippets, gathered for the music dsp community". A long serving site that has recently been revamped. Beware: most of the code there was written a very long time ago, and optimization tricks etc, may not be relevant on modern machines. Also there are lots of code snippets programming languages other than C++ (delphi, java, C#  etc). Could do with some curation.
- [obxd](https://github.com/2DaT/Obxd) - OBxd  is a great sounding oberheim emulation plug-in, written with JUCE. [DiscoDSP have updated it](https://github.com/reales/OB-Xd), and it has also been [ported to work on the web as a WebAudioModule](http://www.webaudiomodules.org/wamsynths/obxd)
- [dexed](https://github.com/asb2m10/dexed) - Dexed is a JUCE frontend to [Raph Levien's "Music Synthesier For Android"](https://github.com/google/music-synthesizer-for-android), which is an excellent DX7 emulation. Also [ported to work on the web as a WebAudioModule](http://www.webaudiomodules.org/wamsynths/dexed)
- [AudioKit SynthOne](https://github.com/AudioKit/AudioKitSynthOne) - SynthOne is a great open source project built using Audiokit,  that will be very interesting to anyone looking to build an iOS synthesiser.
- [AirWindows Plugins](https://github.com/airwindows/airwindows) - A large collection of GUI-less plug-ins open source but supported via patreon [see airwindows site](http://www.airwindows.com/)
- [zita stuff](http://kokkinizita.linuxaudio.org/linuxaudio/index.html) - Fons Adriaensen's linux audio projects offer a lot of great tools for acoustic measurements, spatial audio etc - mostly as jack apps.
- [Webkit's Web Audio API](https://github.com/WebKit/WebKit/tree/main/Source/WebCore/Modules/webaudio) - This is the C++ code for WebKit's implementation of the Web Audio API, as used in Safari.
- [Blink's Web Audio API](https://chromium.googlesource.com/chromium/blink/+/master/Source/modules/webaudio/) - The same thing in Blink (Google chromium).
- [Firefox's Web Audio API](https://searchfox.org/mozilla-central/source/dom/media/webaudio/) - And for Mozilla Firefox.

## Machine Learning / MIR
- [GuitarML](https://github.com/GuitarML) - Very cool project building open source guitar fx/amp simulations using machine learning techniques.
- [NeuralAmpModeler](https://github.com/sdatkinson/neural-amp-modeler) - A similar project, which is also very cool - plug-in built with iPlug2!
- [ONNXRuntime](https://github.com/olilarkin/iPlug2OnnxRuntime) - Microsoft's ONNX Runtime is a ML inference engine that is well documented, has a good build system and can produce small binaries, suitable for Audio Plugins. Here is an iPlug2 example that I prepared.

## Plug-in gui stuff

- [KnobMan, WebKnobMan](https://www.g200kg.com/en/webknobman/gallery.php) - "Safe for work" knob pics and an online tool to generate them.

## Hardware/embedded

- [the owl pedal/module](https://hoxtonowl.com/) - This is a programmable stomp box and eurorack module that I've been working with since the kick starter campaign to launch it. It's a really nice little unit, which you can program in C++, FAUST, Pd or with Max gen~. I find the limited interface with 4 controls makes me think quite carefully about what's important about my DSP algorithm. You can find some patches I made for it (using a mixture of c++ and FAUST) in the [user library](https://www.rebeltech.org/patch-library/patches/authors), and the original code [here](https://github.com/olilarkin/OL-OWLPatches).
- [bela](https://bela.io/) - Bela is a wonderful little SoC + Audio Interface which is pretty revolutionary, allowing super low latency audio and sensor I/O all clocked together, in a tiny package. I wrote the FAUST support class for bela. You can also program it with C++ or libpd, and even supercollider.
- [ELK Audio OS](https://elk.audio/dev-kit/) - A new embedded linux OS & dev kit that runs VST2 & VST3 plugins.
- [mutable instruments](https://github.com/pichenettes/eurorack) - Emilie Gillet's work is inspirational. The code has been [ported to VCVRack](https://github.com/VCVRack/AudibleInstruments/tree/master/src) and to some nice [iOS AUv3s](https://github.com/boourns/Spectrum)
- [pedalvite](https://github.com/EleonoreMizo/pedalevite) - An open source pedal board project from a developer who did a lot of the DSP in the best plugins of the last ~20 years.
- [Daisy](https://www.electro-smith.com/about) - I haven't actually tried Daisy, but it looks brilliant, and I've heard good things. It has a more powerful MCU than the OWL and I really like how the same, cheap board can be plugged into different hardware. 

## Youtubers

- [TheAudioProgrammer](https://www.youtube.com/channel/UCpKb02FsH4WH4X_2xhIoJ1A) - includes a lot of tutorials about JUCE with guest slots on things like web audio.
- [TheChernoProject](https://www.youtube.com/user/TheChernoProject) - although this channel is focused on game development, the [C++ series](https://www.youtube.com/watch?v=18c3MTX0PK0&list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb) is excellent. Highly recommended.
- [Valerio Verlardo - The Sound of AI](https://www.youtube.com/channel/UCZPFjMe1uRSirmSpznqvJfQ) - Valerio has made a very impressive channel and [community](https://valeriovelardo.com/the-sound-of-ai-community/) dedicated to AI and ML topics in Audio

## Interesting Talks

- [Teaching Yourself to Make Music Software: Steve Duda in Conversation | Loop](https://www.youtube.com/watch?v=Cp0rtLaXBio&t=1456s) - an inspiring interview with a great developer about a killer synth.
- [Sean Costello (Valhalla DSP) on reverb design](https://youtu.be/aJLhqfHrwsw) - great talk by another great plugin developer
- [C++ Real-Time Audio Programming with Bela](https://www.youtube.com/playlist?list=PLCrgFeG6pwQmdbB6l3ehC8oBBZbatVoz3) - a very clearly presented course.
- [Vadim Zavalishin - The Art of VA Filter Design, ADC 2018](https://www.youtube.com/watch?v=zPzCLqkQnr0)
- [How Moog Makes Synth Apps: Interview With Geert Bevin, Head Of Software At Moog](https://audiokitpro.com/geert-moog/) - a great interview full of insight

## Places

- [musicdsp mailing list](http://sites.music.columbia.edu/cmc/music-dsp/) - The music DSP mailing list is pretty quiet these days, but it still worth signing up, despite the web 0-1 front page. Every now and again a music DSP legend posts something interesting. 
- [KvR Audio DSP and Plug-in Development Forum](https://www.kvraudio.com/forum/viewforum.php?f=33) - This is probably the most active forum for audio DSP that is not aligned with a particular plug-in framework. There are some very smart people, some mavericks and some plain weirdos who hang out here.
- [JUCE Forums](https://forum.juce.com/) - This is a collection of forums centred around the variety of things that JUCE does. Since there are such a huge amount of people using JUCE to make audio software, there is a lot of good info here.
- [Cockos Forums](https://forum.cockos.com) - Another collection of forums centred around Cockos' tools including one for WDL/iPlug and one for Reaper JS.
- [The audio developer conference (ADC)](https://juce.com/adc) - Whilst the other places mentioned here are all virtual, this is a real conference where you can go and meet real people face-to-face who do audio programming - highly recommended!
- [TheAudioProgrammer Discord server](https://www.youtube.com/watch?v=E3KOptgChdc) - A popular community for discussing audio programming.
- [iPlug2 Forum](https://iplug2.discourse.group/) - forum for iPlug2 discussions
- [Steinberg VST3 Forum](https://forums.steinberg.net/c/developer/vst-3-sdk/) - A forum for the VST3 SDK/format

___

Oli Larkin 2018-2022
www.olilarkin.co.uk

## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
