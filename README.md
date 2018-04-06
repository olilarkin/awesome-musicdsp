# Awesome Music DSP [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
A curated list of my favourite music DSP and audio programming resources, focusing on the C++ programming language. 

I like implementations that allow you to be creative quickly. The less code for the end user (e.g plug-in developer) the better!

Whilst there is some crossover here (for instance JUCE includes DSP functionality, FAUST makes plug-ins), hopefully the grouping makes some kind of sense...

I mainly develop on macOS and Windows so there's not much Linux-audio info here.

Oli Larkin

## Frameworks
- [JUCE](https://github.com/WeAreROLI/JUCE) - JUCE is an undeniably awesome C++ application framework with audio roots. It boasts a vast amount of functionality for the development of music software, including support for almost all plug-in formats and platforms. JUCE is used widely in the music technology industry and it has excellent documentation, code standards, features and support. The JUCE team at Roli organise the [Audio Developer's Conference (ADC)](https://juce.com/adc) which is the most awesome conference around if you like audio programming. What's more all the videos from the three ADCs so far are available [on youtube](https://www.youtube.com/channel/UCaF6fKdDrSmPDmiZcl9KLnQ/videos).
- [WDL](https://github.com/justinfrankel/WDL) - WDL is Cockos' library of reusable C++ code, that is used to power the DAW Reaper, amongst other things. Whilst not traditionally a framework, there is so much good stuff in here, it is highly recommended - although there is next to no documentation, so it's not for the faint of heart. For more info about the various parts of WDL (which can be used independently), check [the Cockos site](https://www.cockos.com/wdl/)
- [WDL-OL/iPlug](https://github.com/olilarkin/wdl-ol) - Not to blow my own physically modelled trumpet, so to speak, but iPlug (originally created by Cockos) is an awesome plug-in framework. I have been maintaining a fork of it since ~2011, which is probably the most widely used and maintained of all of the forks out there. iPlug's syntax is super simple, for example, creating a parameter or a control in the UI is only a single line of C++ code.
- [VSTGUI](https://github.com/steinbergmedia/vstgui) - VSTGUI is Steinberg's cross-platform UI toolkit for audio plug-ins. It is released under a BSD licence, and although it's not my weapon of choice, it's an impressive piece of work and many plug-in developers use it for their products.

## DSP Libraries

- [Gamma](https://github.com/LancePutnam/Gamma) - Gamma is a very awesome C++ DSP framework by Lance Putnam - a developer whose name I've known since the synthedit days. The beauty of Gamma is the conciseness of the implementation of certain techniques. The STFT is a bit of a pain to code, involving overlapping FFT windows etc. How about [this](https://github.com/LancePutnam/Gamma/blob/master/examples/spectral/STFT.cpp) for a concise end user implementation. 
- [FAUST](https://github.com/grame-cncm/faust) - FAUST is a powerful domain specific programming language (DSL) for audio DSP with many options for quickly compiling to different “architectures” including audio plug-ins. FAUST is not interpreted like programming languages such as Puredata/Max/Supercollider/javascript, it is fully compiled to C++ or bytecode - so the FAUST compiler is really a transpiler. This functionality is highly suited to rapid prototyping but can also produce robust and performant binaries. Whilst the rapid prototyping possibilities of FAUST are appealing to me, what I like most about it is the extensive library of high quality DSP routines. Coupled with a concise and expressive syntax, FAUST is a powerful language and definitely worth learning, to use in conjunction with C++. You can check out one of the things I've done with FAUST [here](https://github.com/olilarkin/tambura)
- [HIIR](http://ldesoras.free.fr/prod.html) - HIIR is a seriously cool oversampling library by Laurent de Soras. Oversampling is something we often need in audio DSP, and this library handles it elegantly - providing a variety of classes for low latency IIR half band filtering (including SIMD optimizations). The original code (which was first released in 2005), is a little bit hard to get your head round, but fear not [here is](https://github.com/olilarkin/wdl-ol/tree/iplugquake/IPlug/Extras/HIIR) an updated version with [an example](https://github.com/olilarkin/wdl-ol/blob/iplugquake/IPlug/Extras/Oversampler.h) of how to use it inside an iPlug 2 plug-in.
- [HOALibrary](https://github.com/CICM/HoaLibrary-Light) - As someone who works a lot with spatial audio, it's fantastic that the CICM have released this flexible DSP library for high order ambisonics (HOA) - a spatial audio platform that is becoming more and more relevant thanks to VR.

## Reading
This is a small selection of books that have been helpful to me. There are many others that look absolutely great but I have not used them in anger (yet).

- [Will Pirkle](http://www.willpirkle.com/) - Will Pirkle has written two books that will be invaluable the aspiring audio plug-in developer - "Designing Audio Effect Plug-Ins in C++" and "Designing Software Synthesizer Plug-Ins in C++". For more info [see here](http://www.willpirkle.com/about/books/])
- [Dodge and Jerse - Computer Music: Synthesis, Composition and Performance, 2nd Edition](https://books.google.co.uk/books/about/Computer_Music.html?id=eY_BQgAACAAJ&redir_esc=y) - This is my absolute favourite book to recommend to students studying computer music/audio synthesis. I find the book does not date like some other computer music texts. I find the MUSIC-N style diagrams charming and the techniques are discussed very well.
- [Udo Zölzer (Ed) - DAFX: Digital Audio Effects](https://books.google.co.uk/books/about/DAFX.html?id=DX-mRhkJL74C&source=kp_cover&redir_esc=y) - This is a great book on audio DSP, written by a variety of domain experts, and it includes Matlab code examples.
- [JOS](https://ccrma.stanford.edu/~jos/) - Julius Smith's site and his four books are an amazing resource. Matlab and FAUST code examples included!
- [DAFX Conference Archive](http://www.dafx.de/) - All the papers from the DAFX conference are available online. Another great resource.
- [EarLevel Engineering](http://www.earlevel.com/) - Nigel Redmond's DSP blog contains some very nicely written explanations of a variety of topics.

## Tools
Slightly veering off topic, these are the software tools that I find useful in my audio programming. Xcode 9 and Visual Studio 2017 are the free IDEs that I use, and both are very powerful these days.

- [Cockos Reaper](http://reaper.fm) - In my opinion Reaper is "the programmer's DAW". Whilst it might not be as immediate as some other DAWs, for anyone who wants to try anything experimental in terms of music technology, Reaper is a great place to do it. This is most obvious to me in the area of spatial audio. Reaper supports up to 64 channels per bus/track - that means you can do 7th order ambisonics in Reaper (since a long time ago). Protools and Nuendo have recently announced 3rd order Ambisonics support (16 channel buses).  7 > 3 go figure. Reaper includes its own scriptable assembly language "JS" (which stands for JesuSonic NOT JavaScript). This can really come in handy for quick custom plug-ins. It also has great metering and visualisation utility plug-ins written with JS. Reaper has its own API so you can make plug-ins that integrate very closely with the DAW at a level that VST etc can't provide.
- [Mathworks Matlab](https://www.mathworks.com/products/matlab.html) - Matlab is a great piece of software, even if open source alternatives such as Octave and Python + ... are equally capable. The audio systems toolbox allows you to build VST plug-ins directly from Matlab. Although it's buried deep in the application, you'll find that Matlab audio systems toolbox uses both WDL-OL and JUCE to provide its plug-in functionality. Matlab also has great functionality for plotting curves and loads of other things. 
- [Cycling '74 Max](https://cycling74.com/) - Max is a great environment to use for prototyping audio plug-ins. There are just so many options for integrating different technologies, I highly recommend it - even if nowadays most of the max patches I make only include a few objects!
- [Desmos](https://www.desmos.com) - This is an awesome online graphing calculator. Check out some interactive Casio CZ waveforms that I made [saw](https://www.desmos.com/calculator/te4bzpvav3) [square](https://www.desmos.com/calculator/mclynvox0h) [reso1](https://www.desmos.com/calculator/6659cif7oa)
- [Coliru](http://coliru.stacked-crooked.com/) - This is an online interactive C++ compiler, which can be a very nice and quick way to test out a particular feature of the language, without having to build a binary.
- [Compiler Explorer](https://godbolt.org/) - Compiler explorer is a great tool for checking the assembly code that different compilers will produce.
- [FAUST Editor](http://faust.grame.fr/editor/) - This is an online FAUST IDE and compiler, that lets you test FAUST code with webaudio. You can then tell it to output a zip file with a binary for your preferred platform. This saves you all the trouble of installing FAUST and its dependencies on your local machine.

## Open source projects to work with or look at for "inspiration"
I got into programming in C/C++ by making objects for Max and Synthedit. Learning how to use the SDKs for one of those or for one of the following open source packages is a nice way to start in my opinion, since you don't need to think about too many things. What's more - these great projects all show you how you can go about certain tasks... the code is there for you to look at. It might take you a while to find it, and sometimes the code might be hard to understand, but they all have oscillators, filters etc. There are many third party objects as well, that are also open source. Don't just copy stuff - you won't learn and you also probably violate the license, which is bad karma!

- [puredata](http://msp.ucsd.edu/software.html) - I don't think this needs an introduction! Also check out libpd, which you can use as a DSP library in your C++ audio plug-in etc.
- [supercollider](https://github.com/supercollider/supercollider) - Likewise, but make sure you look at the scsynth part for DSP stuff.
- [csound](https://github.com/csound/csound) - CSound has seen a renaisannce of late and can be used as an embedable DSP library
- [vcvrack](https://github.com/VCVRack/Rack) - Wow... i was seriously impressed when VCVRack was released earlier this year. Whilst the other items in this list have been around awhile and have somewhat arcane code-bases, this is pretty new and the API is very clean and simple. I think making a VCVRack module it is a great way to get into audio programming.
- [mutable instruments](https://github.com/pichenettes/eurorack) - Olivier's Gillet's work is very inspiring. Although written for microcontrollers, there is so much to learn from here. And it's [ported to VCVRack](https://github.com/VCVRack/AudibleInstruments/tree/master/src) so you can try it on the desktop.

## Places
Here are a few links to the various corners of the internet and real-world where you might like to hang out if you like this kind of geeky stuff...

- [musicdsp mailing list](http://sites.music.columbia.edu/cmc/music-dsp/) - The music DSP mailing list is pretty quiet these days, but it still worth signing up, despite the web 0-1 front page. Every now and again a music DSP legend posts something interesting. 
- [KvR Audio DSP and Plug-in Development Forum](https://www.kvraudio.com/forum/viewforum.php?f=33) - This is probably the most active forum for audio DSP that is not aligned with a particular plug-in framework. There are some very smart people, some mavericks and some plain weirdos who hang out here.
- [JUCE Forums](https://forum.juce.com/) - This is a collection of forums centred around the variety of things that JUCE does. Since there is such a huge amount of people using JUCE to make audio software, there is a lot of good info here.
- [Cockos Forums](https://forum.cockos.com) - Another collection of forums centred around Cockos' tools including one for WDL/iPlug and one for Reaper JS.
- [The audio developer conference (ADC)](https://juce.com/adc) - Whilst the other places mentioned here are all virtual, this is a real conference where you can go and meet real people face-to-face who do audio programming - highly recommended! Having been to a lot of more academic conferences, I can say this one is well worth the cost of entry!

___

Oli Larkin 2018  
www.olilarkin.co.uk

## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
