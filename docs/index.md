# Frame rate versus temperature on a mid-range Android phone

For two weeks I logged the same 30-minute play session on a Helio G99 phone
(8 GB RAM, 5,000 mAh, Android 14) to see how frame rate and skin temperature
actually move together. Everything below is measured, not guessed: frame times
came from `dumpsys SurfaceFlinger --latency`, and I took a cheap IR thermometer
reading on the back cover every two minutes.

## The pattern

Frames stay flat and the phone stays cool for the first 8-9 minutes. Then the
back cover reaches roughly 41 C and the governor starts trimming: 60 fps drifts
to 52, then settles around 47. Heat does not climb in a straight line either -
it plateaus near 43 C, because the SoC throttles itself well before the chassis
becomes unpleasant to hold.

The useful finding is that **temperature leads frame rate by about 90 seconds**.
If I watch the thermometer instead of the FPS counter, I can predict a drop
before it happens, which is exactly when I stop and let the phone cool down for
five minutes.

## What actually helps

- Playing without a case: 2-3 C cooler after 15 minutes, and about 3 fps steadier.
- Charging while playing: +5 C and a drop of roughly 8 fps. Never worth it.
- Room temperature matters more than any in-game graphics setting.

Longer write-ups, screenshots and the raw tables live in
[my game notes](https://ekagamenotes.blogspot.com).
