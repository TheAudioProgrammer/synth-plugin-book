# Creating Synthesizer Plug-Ins with C++ and JUCE

This is the source code that accompanies the book [Creating Synthesizer Plug-Ins with C++ and JUCE](https://theaudioprogrammer.com/synth-plugin-book) by Matthijs Hollemans, available for purchase from [The Audio Programmer](https://theaudioprogrammer.com/synth-plugin-book) as PDF and EPUB.

![The book cover](book-cover.jpg)

This 370-page book teaches step-by-step how to design and build a software synthesizer plug-in that can be used in all the popular DAWs such as Logic Pro, Ableton Live, REAPER, FL Studio, Cubase, Bitwig Studio, and others.

The plug-in is made using industry standard tools for audio programming: the JUCE framework and the C++ programming language. You'll learn all the fundamentals of writing audio plug-ins in general and synths in particular, in an easy-to-follow guide that is light on math and heavy on being practical.

If you don't have the book yet, you can read free sample chapters at [theaudioprogrammer.com/learn/synth-plugin-book](https://theaudioprogrammer.com/learn/synth-plugin-book) to see if you like it.

## How to use this repo

For each chapter there is a folder with the finished source code. Open the **JX11.jucer** file in **Projucer** and click the export button to open the project in your IDE.

The **Finished Project** folder contains the synth plug-in in its entirety, with added source code comments (it does not include the UI code from Chapter 13).

Want to know what the synth sounds like? Check out a few examples in the **Audio Demos** folder.

## Found a bug or have a question?

First, please [check the errata](Errata.markdown) to see if the issue has already been covered.

If not, refer to the [list of open issues](https://github.com/TheAudioProgrammer/synth-plugin-book/issues) and submit a new issue if you can't find your question in the list.

Also make sure to join [The Audio Programmer community on Discord](https://www.theaudioprogrammer.com/discord). This is a great place to chat about all things related to audio programming. You can find me there as `matthijs`.

## Source code license

The book is copyright 2022-2023 M.I. Hollemans, all rights reserved.

The source code in this repo is licensed under the terms of the [MIT license](LICENSE.txt).

The JX11 synth from the book is based on the MDA JX10 synthesizer, originally written by Paul Kellett of maxim digital audio. The factory presets included in the synth are designed by Paul Kellett with additional patch design by Stefan Andersson and Zeitfraktur, Sascha Kujawa.

JUCE is copyright © Raw Material Software.

The Lato font is copyright (c) 2010-2014 Łukasz Dziedzic and is licensed under the SIL Open Font License.
