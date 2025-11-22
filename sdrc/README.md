## Notes from Visit Nov 22, 2025

* UHF tone squelch (TX) is intermittent into Bruce's HT. Martin was seeing this too.
* How much deviation is on the UHF PL tone?  The -25dB configured level seems high.
* Needed to max the pot on VHF audio input initially, and also added +6dB of software gain. So we want to get more HW gain
so we can take out the +6dB software. Should add 12dB analog gain as an option (special for Yaesu series which are known to have low audio output)
* Switch to audio taper pots on all gain adjustments.
* Add ground screw post. Ground to chassis.
* Consider 3 +6dB ranges with jumpers (i.e. +6dB, +12dB, and +18dB)
* Add asSoft limiter on receive input (1/4 second release)
* Lockout
  - Need to fix the problem when lockout is extended by any
    transmisison.
  - At the start of the lockout we need an audio indication.
  - At the end of the lockout we should go into ID mode (as 
    an audio indication).

