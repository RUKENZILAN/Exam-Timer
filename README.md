# Exam-Timer
A secure, easy-to-use standalone exam countdown timer for lecturers and
exam invigilators. It runs entirely in the browser — no installation, no
internet connection, and no data ever leaves the device.
The app is a single self-contained HTML file (`public/exam-timer.html`) with
all styles and scripts inlined. Open it in any modern browser and it just
works.
---
Features
Course name — label the exam so students and staff know which paper is
being timed.
Start & end time — set the exam window using native time pickers. The
timer counts down to the configured end time.
Pause & Resume — pause the countdown at any time (e.g. for a
disruption or break) and resume exactly where it left off.
Reset — clears the current exam and returns to the setup screen
(confirmation prompt prevents accidental resets).
Warning threshold — choose how many minutes before the end the clock
turns amber, then red in the final minute.
Progress bar — visual indicator of how much of the exam has elapsed.
Audible alert — a beep plays when time is up.
Fullscreen mode — one-click fullscreen for display on a projector or
classroom screen.
Close protection — the browser warns if you try to close or refresh the
tab while an exam is running.
100% offline & private — no servers, no accounts, no tracking.
---
Getting started
Option 1 — Open the file directly
Locate `public/exam-timer.html`.
Double-click it, or open it with any modern browser
(Chrome, Edge, Firefox, Safari).
That's it. No build step or dependencies required.
Option 2 — Serve it from the project (dev)
If the project is running, the file is served from the `public/` directory and
is available at:
```
/exam-timer.html
```
For example, on the local dev server:
```
http://localhost:8080/exam-timer.html
```
---
How to use
Enter the course name (e.g. "Introduction to Algorithms").
Set the start time and end time (pre-filled with the current time
and a 90-minute default).
Set the warning value — the number of minutes before the end when the
clock should turn amber (default is 10).
Click Start Exam. The countdown begins immediately.
Use Pause to halt the timer and Resume to continue.
Use Reset to stop and clear the current exam.
Use Fullscreen to expand the display for a projector or classroom
screen.
The clock colour changes as time runs out:
Stage	Colour	When
Normal	Blue	More than the warning threshold left
Warning	Amber	Within the configured warning window
Critical	Red	Final 60 seconds
Finished	Red	Time is up (screen flashes + beep)
---
Security & privacy
No network requests. The page makes zero outbound calls. All logic runs
locally in the browser.
No data storage. Nothing is written to disk, cookies, or remote
servers. Closing the tab clears all state.
Input sanitisation. The course name is sanitised before display and is
inserted via `textContent`, which prevents injection of HTML/scripts
(XSS-safe).
Accidental-close guard. A `beforeunload` prompt protects against losing
a running exam by accidentally closing or refreshing the tab.
No third-party dependencies. There are no external libraries, fonts, or
trackers loaded — the file is fully self-contained.
---
File overview
```
public/exam-timer.html   # The entire application (HTML + CSS + JS, one file)
README.md                # This document
```
The application logic is wrapped in a single IIFE (immediately-invoked
function expression) with `"use strict"`, keeping the global scope clean.
---
Browser support
Tested in all evergreen browsers: Chrome, Edge, Firefox, and Safari. Requires
JavaScript enabled. Audio playback of the completion beep follows standard
browser autoplay rules (triggered by the user's Start click, so it works
without extra permissions).
---
License
This project is licensed under the MIT License.
```
MIT License

Copyright (c) 2026 Exam Timer

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
