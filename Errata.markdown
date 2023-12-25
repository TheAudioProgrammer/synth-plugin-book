# Errata

This is a list of known mistakes and bugs in the book *Creating Synthesizer Plug-Ins with C++ and JUCE* and/or the accompanying source code.

---

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

---
