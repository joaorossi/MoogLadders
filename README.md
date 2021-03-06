# Moog Ladder Filters

This project contains digital implementations of the classic 4-pole, 24 dB/octave analog filter introduced in 1965. This filter is known to add a nice character to any instrument, synthesized or acoustic. 

The ladder structure consists of four one-pole filters and a global negative feedback loop. Several academics have attempted to discretize this filter, and their efforts are documented in the research/ directory. Most of the implementations are based on these papers in one form or another.

The filter classes do not rely on the use of any external libraries and can be used with little to no modification in other DSP projects. Every filter has been modified from its original implementation for clarity and performance. The project includes a test app that will pass white noise through any of the filters. 

# Filter Tuning & A Word of Warning
Each model is a bit unique. The newest is from 2015 while the oldest dates back over 20 years. Some try to remain true to their analog counterpart, where others are more approximate. The filters have not been rigorously verified for all combinations of cutoff, resonance, and sampling rate. Some are purposely built to self-oscillate, but beware the occasional blow-up with parameters that exceed some undiscovered value. 

# Models & Licenses

“Closed Source Friendly” indicates if the individual license permits redistribution in a closed-source product (like a VST plugin). Filtered output audio is fair game for any kind of sample library or music production, commercial or otherwise. In the case of copyright-only code, it is possible to contact the original author to request an explicit license.

Implementation | License | Original Source | Closed-Source Friendly
------------- | ------------- | ----------------- | -----------------
Stilson | Copyright | Moog~ by D. Lowenfels | -
Oberheim | Copyright | Will Pirkle | -
Simplified | Copyright | DAFX Example | - 
Microtracker | Copyright | Magnus Jonsson | -
Aaron | Copyright | Via Author | -
Huovilainen  | LGPLv3 | CSound | As Dynamic Lib
Improved | ISC | Via Author | Yes
RKSimulation | BSD | Bob~ by Miller Puckette | Yes
MusicDSP | Unlicensed | MusicDSP.org | Maybe

## ToDo

* The Huovilainen and Simplified models need to be correctly oversampled and nyquist filtered
* Several filters have extra parameters that could be exposed (drive, thermal coefficients, Q, etc)
* Many filters could be easily modified for HPF output
* Denormal prevention
* (Longer term) Filter response graphs
