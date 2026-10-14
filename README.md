# obs-browser-timer

This is a simple transparent web timer designed to be used as a browser source in OBS. Does some automatic changing of formats when below 1 hour and below 20 seconds remaining.

# Usage

In OBS, add a new browser source and add an URL from the examples below.

Recommended OBS browser source settings

    width=400
    height=100
    Shutdown source when not visible. This will let you restart the timer by hiding and unhiding it.

Parameters

    s (seconds): Optional. Duration of the timer in seconds. For leeway, 3 seconds will be added to user assigned values.
    c (color): Optional. Text color of the timer in hex format (e.g., c=FF0000 for red). Default is a pastel yellow.
    a (alarm): Optional. Alarm sound to play when the timer ends. Defaults to 1 (sounds/1.mp3); use 0 to disable or 2 for sounds/2.mp3.
    v (volume): Optional. Volume of the alarm sound, ranging from 0 to 100. Default is 20.

# Examples
Note: most browsers require you to click somewhere on the page at least once for the sound to play successfully. At time of writing, OBS does not require any interaction for the sound to play, but please test on your own.
The full link format with default parameters is
```https://nakomaru.github.io/obs-browser-timer/timer.html?a=1&v=20&c=FFF788&s=22```

simple 2 minute timer with default settings -> [timer.html?s=120](https://nakomaru.github.io/obs-browser-timer/timer.html?s=120)

2(+3) second timer with alarm 1, 20% volume -> [timer.html?a=1&s=2](https://nakomaru.github.io/obs-browser-timer/timer.html?a=1&s=2)

2(+3) second timer with alarm 2, 75% volume -> [timer.html?a=1&v=75&s=2](https://nakomaru.github.io/obs-browser-timer/timer.html?a=2&v=75&s=2)

1 hour timer, white text -> [timer.html?c=FFFFFF&s=3600](https://nakomaru.github.io/obs-browser-timer/timer.html?c=FFFFFF&s=3600)

# Licenses

1.mp3 -> notification1-freesound.wav by Thoribass - [Link](https://freesound.org/s/253595) - License: Attribution 4.0

2.mp3 -> 09156 accent chime login.wav by Robinhood76 - [Link](https://freesound.org/s/528475/) - License: Attribution NonCommercial 4.0

Everything else -> CC0

# timer-presentasi
