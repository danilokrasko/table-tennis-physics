# Table Tennis Physics

A 15 second table tennis rally between FOXIK and a robot, built with Opus 5.5. One HTML file, three.js, no 3D models.

Open `index.html` in Chrome or Edge. It loads three.js from the internet, so you need a connection.

## What is inside

- **The rally.** 5 shots: a sidespin serve, two drives, a 4,000 rpm loop and a 94 km/h smash. The ball flies by physics: gravity, air drag, the Magnus force and bounces off the table.
- **Spin lab.** Scroll down under the video. Pick sidespin, topspin or backspin and drag the slider. The same serve is launched every time, so you see only what the spin changes. The dashed line is the same shot with no spin.
- **Render MP4.** The button records the 15 second video in your browser and downloads it (needs a browser with WebCodecs, like Chrome).

## Numbers from the simulation

- Serve: 30 km/h, 2,600 rpm sidespin, curves 31 cm compared to the same serve with no spin
- Loop: 4,000 rpm topspin. Without the spin the ball would miss the table by 33 cm
- Smash: 94 km/h

## What you can change

In `index.html`, find this line:

```js
const W_SERVE = 2600, W_LOOP = 4000, W_SMASH = 800, W_D2 = 2200, W_D3 = 2500;
```

These are the spin values in rpm for each shot. The solver finds the launch speed for each shot, so the rally still works after you change them. Large changes can break the choreography, because the players' timing is set by hand.

## Limits

This is a simulation, not a real match.

- I chose the spin values by hand. The simulation does not decide how much spin a player would use.
- The spin model is real Magnus math, but simplified: one lift coefficient, and spin drops 30% on every bounce.
- Forces and speeds on screen come from the same simulation that moves the ball.

Made by [@foxik9b](https://x.com/foxik9b).
