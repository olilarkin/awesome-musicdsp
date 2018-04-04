# awesome-musicdsp [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
A curated list of my favourite music DSP and audio plug-in frameworks, focusing on the C++ programming language. 

I like implementations that allow you to be creative quickly - less code for the end user (e.g plug-in developer) the better!

## Frameworks

- [JUCE](https://github.com/WeAreROLI/JUCE) - JUCE is an undeniably awesome C++ application framework with audio roots. It boasts a vast amount of functionality for the development of audio and music software, including support for almost all audio plug-in formats and platforms. JUCE is used widely in the music technology industry and it has excellent documentation, code standards, functionality and support. The JUCE team at Roli organise the [Audio Developer's Conference (ADC)](https://juce.com/adc) which is the most awesome conference around if you like audio programming. What's more all the videos from the three ADCs so far are available [on youtube](https://www.youtube.com/channel/UCaF6fKdDrSmPDmiZcl9KLnQ/videos).
- [WDL](https://github.com/justinfrankel/WDL) - WDL is Cockos' library of reusable C++ code, that is used to power the DAW Reaper, amongst other things. Whilst not traditionally a framework, there is so much good stuff in here, it is highly recommended - although there is next to no documentation, so it's not for the faint of heart. For more info about the various parts of WDL (which can be used independently), check [the Cockos site](https://www.cockos.com/wdl/)
- [WDL-OL/iPlug](https://github.com/olilarkin/wdl-ol) - Not to blow my own physically modelled trumpet, so to speak, but iPlug (originally created by Cockos) is an awesome plug-in framework. I have been maintaining a fork of it since ~2011, which is probably the most widely used and maintained. iPlug's syntax is super simple, for example, creating a parameter or a control in the UI as a single line of code.

## DSP Libraries

- [Gamma](https://github.com/LancePutnam/Gamma) - Gamma is a very awesome C++ DSP framework by Lance Putnam - a developer whose name I've known since the synthedit days. The beauty of Gamma is the conciseness of the implementation of certain techniques. The STFT is a bit of a pain to code, involving overlapping FFT windows etc. How about [this](https://github.com/LancePutnam/Gamma/blob/master/examples/spectral/STFT.cpp) for a concise end user implementation. 
- [FAUST](https://github.com/grame-cncm/faust) - FAUST is a powerful domain specific programming language (DSL) for audio DSP with many options for quickly compiling to different “architectures” including audio plug-ins. FAUST is not interpreted like programming languages such as Puredata/Max/Supercollider, it is fully compiled - so the FAUST compiler is really a transpiler. This functionality is highly suited to rapid prototyping but can also produce robust and performant binaries. Whilst the rapid prototyping possibilities of FAUST are appealing to me, what I like most about it is the extensive library of high quality DSP routines. Coupled with a concise and expressive syntax, FAUST is a powerful tool and definitely worth learning, to use in conjunction with C++.

## License

[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
