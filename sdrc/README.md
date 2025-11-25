## Notes from Visit 2025-11-25

* Swapped digital boards and installed firmware **V1.1 2025-11-23**.
* A release was created in GitHub to mark the firmware version (v1.1)
in production.
* New code addressed a problem with the lockout.
* Changed courtesy tone level to -15dB.
* Changed COS inactivate time to 100ms from 150ms to shorten 
static crash at end of transmission.
* Tested with Dan W1DAN, validated timeout, validated DTMF kill.
* Briefly switched over to soft CTCSS detect on the VHF side (detect
level set to -65dB). Functionality was good, but didn't seem faster
than the current setup. Switched back to the hardware detect.
* Dan suggested that we change the lockout logic so that it re-checks
for an active carrier right at the end of the lockout period. If 
the carrier is still active (for example, if we are experiencing a continuous key-down) then the lockout would be extended.
* Determined that the faint "hum" heard is only present during 
VHF receive. This, along with some listening tests, suggests that 
the "hum" may actually be the 123 Hz PL tone bleeding through the
controller. Need to review the high-pass filter on the bottom of
the audio passband.

## Notes from Visit 2025-11-22

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

