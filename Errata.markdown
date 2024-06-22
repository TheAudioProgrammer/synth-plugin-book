# Errata

This is a list of known mistakes and bugs in the book *Creating Synthesizer Plug-Ins with C++ and JUCE* and/or the accompanying source code.

## Chapter 3: Nyquist limit

Chapter 3, page 66 says:

> The maximum frequency the signal can contain is known as the Nyquist limit. When using a sampling rate of 44.1 kHz, the Nyquist limit is 22.5 kHz, and the sampled signal can faithfully represent any frequencies lower than 22500 Hz — well above the hearing range of humans. But frequencies higher than 22.5 kHz won't work.

The Nyquist limit at a sampling rate of 44.1 kHz is 22.05 kHz or 22050 Hz, not 22500. [Thanks @metajack](https://github.com/TheAudioProgrammer/synth-plugin-book/issues/4)

## Chapter 6: The sawtooth oscillator

Chapter 6, page 125 says:

> The while loop adds up sine waves until it reaches the Nyquist limit. The sine values are accumulated in the variable `y`.

The variable is not named `y` but `output`.

## Chapter 11: Modulation

Chapter 11, page 288 says to add a new method `updatePeriod` and then replace the corresponding lines of code in `Synth::render` with call to `updatePeriod(voice);`

However, at the top of p.289 the code still does the following:

```c++
for (int v = 0; v < MAX_VOICES; ++v) {
    Voice& voice = voices[v];
    if (voice.env.isActive()) {
        voice.osc1.period = voice.period * pitchBend;
        voice.osc2.period = voice.osc1.period * detune;
        voice.glideRate = glideRate;              // add this line
    }
}
```

It should be:

```c++
for (int v = 0; v < MAX_VOICES; ++v) {
    Voice& voice = voices[v];
    if (voice.env.isActive()) {
        updatePeriod(voice);
        voice.glideRate = glideRate;
    }
}
```

The synth works OK with the old lines, but using `updatePeriod` here is cleaner.

(Also note that `updatePeriod` does not actually have to be declared `inline` since it's placed inside the class definition in the .h file. Such methods are considered inline by default.)
