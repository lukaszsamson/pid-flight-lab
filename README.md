# PID Flight Lab

**Live:** https://pid-flight-lab.netlify.app

An interactive, single-page lesson set on PID controller tuning. You tune the altitude-hold loop of a simulated 1 kg quadcopter and watch what each gain does.

## What it covers

Twelve lessons, each loading a setup that shows one real-world tuning problem:

1. The control loop
2. P only: droop and oscillation
3. D as a damper
4. I removes steady-state error, and too much of it overshoots
5. Stability: closed-loop poles, phase and gain margins, Ziegler–Nichols helper
6. Integral windup and anti-windup (clamping, back-calculation)
7. Derivative kick, and derivative on measurement
8. Sensor noise and the derivative filter
9. Dead time
10. Disturbances, load changes and feedforward
11. Flight test challenge (scored)
12. A practical tuning recipe

## The model

- **Plant:** vertical dynamics `m·z'' = T − m·g − c·z' + wind`, with drag `c = 0.8 N·s/m`, first-order motor lag (80 ms), thrust limited to 0–25 N, and a ground contact.
- **Sensor:** configurable Gaussian noise and transport delay.
- **Controller:** discrete PID at 10–200 Hz with a first-order derivative filter, derivative on error or measurement, three anti-windup modes and optional hover feedforward.
- **Stability panel:** closed-loop poles of the linearized loop (2nd-order Padé for delay, half a sample for the zero-order hold) and margins from the exact frequency response.

## Running

Open `site/index.html` in a browser. There is no build step.

## Deployment

Netlify deploys `site/` on every push to `main` (see `netlify.toml`).

## License

Apache License 2.0. See [LICENSE](LICENSE).
