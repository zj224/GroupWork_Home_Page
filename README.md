# M&AE 3260 GroupWork WebApps

Browser-based versions of the weekly MATLAB group assignments for **M&AE 3260: System Dynamics & Controls** at Cornell University.

This repo is the **home page**: a landing page with a card for each week's assignment. Each assignment is a single, self-contained web page in its own repo (listed below). Students open a link and work through the problems. There's nothing to install, no MATLAB license to set up, and no difference between Windows, macOS or ChromeOS.

## Why

The original assignments were MATLAB Live Scripts, which caused recurring problems in a large class:

- **Lag:** Live Scripts re-ran slowly, especially interactive plots and animations.
- **Version and OS inconsistencies:** the same script behaved differently across MATLAB releases and operating systems, and a lot of class time went to troubleshooting setups instead of learning.

Rebuilding each assignment as a web page removed both problems: it runs instantly in any modern browser, and every student sees the same thing.

## Impact

- Used by **200+ students** in M&AE 3260.
- **99%** of students preferred the WebApp versions to MATLAB.
- The instructor **fully retired the MATLAB versions** in favor of these.

## Assignments

| Assignment | What students do | Repo |
|---|---|---|
| **5W: Lab 2 Prep, Logarithmic Decrement** | Derive the log decrement for N > 1 periods, implement it, fit it to real lab data, and explore how sensitive the estimate is to ±50% errors. | [GroupWork_5W_Lab2Prep_LogDec](https://github.com/mae3260/GroupWork_5W_Lab2Prep_LogDec) |
| **5F: Frequency Response** | Read amplitude ratio and phase off Bode plots, turn them into x(t), go from time histories back to frequency response, and overlay Bode plots for different damping. Includes an animated spring-mass-damper. | [GroupWork_5F_Frequency_Response](https://github.com/mae3260/GroupWork_5F_Frequency_Response) |
| **6W: Bode Plot Generator** | Build a transfer function from zeros, poles and gain, and see its Bode plot update. | [WebApp_GW_Learning_Tools](https://github.com/mae3260/WebApp_GW_Learning_Tools) |
| **6F: Passive Suspension Design** | Derive transfer functions for a quarter-car suspension, pick a damping value that satisfies position, acceleration and shock-travel specs on a Bode plot, then check the design with bumpy-road and speed-bump simulations. | [Groupwork_6F_Suspension_Design](https://github.com/mae3260/Groupwork_6F_Suspension_Design) |
| **7F: Advanced State Space (Loudspeaker)** | Build the A, B, C, D matrices for a loudspeaker, view the MIMO Bode plots, and **listen** to raw vs. filtered audio while tuning a noise filter. | [Groupwork_7F_Advanced_State_Space](https://github.com/mae3260/Groupwork_7F_Advanced_State_Space) |

The live version of every assignment is linked from the home page.

## Features

Every assignment page shares the same core features:

- **Interactive plots.** Zoom, pan and hover on Bode plots and time responses. Log axes are labeled the way MATLAB labels them.
- **Typed-in math.** Students enter expressions like `1.02*sin(0.5*t - 0.102)` or transfer-function coefficients, and the page evaluates and plots them.
- **Rendered equations.** Theory sections are typeset with KaTeX.
- **Simulations in the browser.** ODEs are integrated with RK4, the animations are physics-driven, and 7F plays and filters audio with the Web Audio API.
- **Autosave.** Progress is saved in the browser, so a refresh doesn't wipe a group's work.
- **One-click PDF submission.** Answers, discussion responses and plots are exported to a single PDF, with the option to attach extra PDFs such as hand derivations.

## Tech stack

Plain HTML, CSS and JavaScript. There's no framework and no build step, and each page is a single `index.html` file.

| Library | Used for |
|---|---|
| [Plotly.js](https://plotly.com/javascript/) | Interactive plots |
| [math.js](https://mathjs.org/) | Parsing and evaluating student-entered expressions |
| [KaTeX](https://katex.org/) | Equation rendering |
| [jsPDF](https://github.com/parallax/jsPDF) and [pdf-lib](https://pdf-lib.js.org/) | Generating and merging the submission PDF |

All libraries load from a CDN. Each page is deployed on its own as a static site on Netlify.

## Running locally

Open `index.html` in a browser. That's it. The same works for any of the assignment repos.

## Author

**Kelly Jiang**, Cornell University. Built for M&AE 3260 System Dynamics & Controls.
