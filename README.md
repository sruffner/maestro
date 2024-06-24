# Maestro

<mark>**_NOTE: I am no longer actively developing** Maestro/RMVideo**. I have made this repo available for anyone in the
neuroscience community that continues to use the application and might wish to fork the repo to adapt or modify the
program for their own purposes._**</mark>

**Maestro** is a Windows® application developed in Stephen G. Lisberger's laboratory at Duke University to conduct a 
wide variety of behavioral and neurophysiological experiments focusing on smooth pursuit eye movements, the vestibular 
ocular reflex (VOR), and certain other aspects of the visual system. It provides real-time data acquisition and stimulus 
control to meet the particular research needs of the laboratory, and it is specifically tailored to the experimental 
apparatus employed there.

**Maestro** experiments record behavioral and neuronal responses to visual stimuli. Eye movement and neurophysiological
data are recorded at 1KHz. Some experimental protocols require the ability to adapt predefined target trajectories 
during runtime in accordance with the subject’s behavioral response. The potential complexity of experiments that 
animate multiple targets simultaneously, along with the need to adjust target trajectories during runtime, place a 
premium on efficient communications with the relevant hardware and demand sub-millisecond responsiveness.

**Maestro** was developed to meet these operational demands. Over the years it has evolved from a distributed program 
with components hosted on a UNIX workstation and two DOS PCs to an all-in-one Windows NT/2000/XP application running on 
a single machine. In its latest form, the application is once again distributed in nature, consisting of three 
functional modules. The user defines, modifies, and executes experimental protocols via a graphical user interface 
(GUI). The GUI module, acting as the “master”, sends protocol information and issues a variety of commands to the 
experiment control and hardware interface. The hardware controller is the time-intensive component of **Maestro** and
does most of the heavy lifting: communication with PC peripheral devices, controlling frame-by-frame animation of 
visual targets during a trial, recording and saving data streams, and providing feedback to the GUI in the form of 
status messages, data traces, and current eye and target positions. The controller is spawned by the GUI module at 
startup and runs as a "real-time", kernel-level process within IntervalZero's RealTime Extension (RTX) to 
Windows. The two modules run on a Windows workstation and communicate over interprocess shared memory. A third 
functional module, the OpenGL application **RMVideo**, drives the primary visual stimulus display -- a large, 
high-performance CRT monitor. This module runs on a separate Linux workstation and communicates with the **Maestro** 
hardware controller over a private, dedicated Ethernet link.


## User Guide
An [online user's guide](https://sites.google.com/a/srscicomp.com/maestro/home) provides a thorough introduction to the 
program, detailed information about system requirements and supported hardware, usage instructions, a complete version 
history, and a downloads page where you can get the latest release. The online guide also covers RMVideo, which is 
Maestro's workhorse visual stimulus platform (running on a separate Linux workstation); JMWork, a Java application that
reads and edits Maestro data files (no longer supported); and several Maestro-related Matlab utilities.

## Installation
TODO

### Related Matlab Utilities
TODO

## Building/Packaging
TODO

## License
**Maestro** was created by [Scott Ruffner](mailto:sruffner@srscicomp.com). It is licensed under the terms of the MIT license.

## Credits
**Maestro** was developed with funding provided by the Stephen G. Lisberger laboratory in the Department of
Neurobiology at Duke University. It evolved from Dr. Lisberger's UNIX-based **Cntrlx** application.


