# M&AE 3260 GroupWork WebApps

Browser-based versions of the weekly MATLAB group assignments for **M&AE 3260: System Dynamics & Controls** at Cornell University.

**Live site: [gwhome.netlify.app](https://gwhome.netlify.app)**

This repo is the **home page**: a landing page with a card for each week's assignment. Each assignment is a single, self-contained web page. Students open a link and work through the problems. There's nothing to install, no MATLAB license to set up, and no difference between Windows, macOS or ChromeOS.

## Why

The original assignments were MATLAB Live Scripts, which caused recurring problems in a large class:

- **Lag:** Live Scripts re-ran slowly, especially interactive plots and animations.
- **Version and OS inconsistencies:** the same script behaved differently across MATLAB releases and operating systems, and a lot of class time went to troubleshooting setups instead of learning.

Rebuilding each assignment as a web page removed both problems: it runs instantly in any modern browser, and every student sees the same thing.

## Impact

- Used by **200+ students** in M&AE 3260.
- **99%** of students preferred the WebApp versions to MATLAB.
- The instructor **fully retired the MATLAB versions** in favor of these.

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

## Author

**Kelly Jiang**, Cornell University. Built for M&AE 3260 System Dynamics & Controls.
