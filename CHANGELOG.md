# CHANGELOG for Pink

## NEXT

Updated

* pink.io.midi
  * namespace redesigned for use with :as syntax when requiring [Issue #5,
    changes contributed by @triss]
  * find-device fixed to work on Windows [Issue # 3, fix contributed by @triss]


## 0.2.1

* removed use of Zach Tellman's primitive-math and added implementation of
  not== to pink.util based on his work

## 0.2.0

New 

* pink.oscillators
  * pulse - unipolar pulse generator 
* pink.delays
  * samp-delay - non-interpolating delay line with fixed delay-time in
    samples.
  * frac-delay,fdelay - interpolating (fractional) delay lines with fixed
    delay-time in samples/seconds.
  * delay-read,delay-readi - higher order function for creating indexed and
    interpolated delay line reader functions
* pink.filters
  * statevar - state-variable filter: returns multi-channel audio with
    high-pass, low-pass, band-pass, and band-reject versions of input signal
  * comb - feedback comb filter
  * combinv - feedforward comb filter
* pink.util
  * gen-recur - macro for generator recur statements that takes care of
    incrementing indx
  * get-channel - Audio Function that gets a channel of audio from a
    multi-channel generating audio function
  * with-signals - macro that destructures multi-channel audio function signal
    into separate single-channel audio function signals
  * merge-signals - function that merges output of two separate audio function
    signals ino a single stereo audio function signal
  * apply-stereo - destructures a stereo audio signal, applies func to each 
    channel, and merges back into a stereo audio function signal
* pink.effects.chorus
  * chorus - added stereo chorus effect
* pink.effects.reverb
  * freeverb - implementation of freeverb reverb processor
* pink.effects.ringmod
  * ringmod - Implementation of Julian Parker's digital model of a 
    diode-based ring modulator
* Updated to Clojure 1.7.0

Fixed

* pink.delays
  * adelay - calculation for delay time was off by buffer-size, reimplemented
    using new samp-delay
* pink.envelopes
  * adsr - fixed error when \*done\* and \*duration\* were nil 

## 0.1.0

* Initial Release
