---
title: "Keyboard PCB"
excerpt: "PCB Design of a keyboard using MX switches and a RP2040<br/><img src='/images/kb_pcb.png'>"
collection: portfolio
---

![Keyboard PCB](http://localhost:4000/images/kb_pcb.png)

I designed a custom mechanical keyboard PCB from the ground up using KiCAD. I wanted to learn the basics of PCB design and I felt that this design oject would be a good start. This project encompasses optimizing component layout and tracks, dual-layer PCB routing and component selection.

## Specification:
* Engineered a compact, 75% compact mechanical keyboard that features a 84-key matrix layout. The matrix includes a 1N4148 switching diode per node for full N-key Rollover (NKRO) and prevent ghosting.
* Integrated a robust yet minimal RP2040 circuit design that features a 3V 16MB serial flash memory chip with SPI interface, 12 MHz crystal oscillator with CMOS output and a debug header. Design also includes a robust USB-C interface complete with a TVS diode array for ESD protection, terminating resistors and decoupling capacitors.
* Designed a clean dual-layer PCB layout in KiCAD with solid ground planes to reduce EMI, with careful consideration of track width and clearances to comply with Design for Manufacturing tolerances.

This project helped develop my understanding of the fundamentals of PCB design. It taught me how to use KiCADs and the many factors that come into play when considering component placement, layout and track routing.

![Keyboard PCB Back Layer](http://localhost:4000/images/kb_pcb_layer_one.png)

![Keyboard PCB Front Layer](http://localhost:4000/images/kb_pcb_layer_two.png)

![Keyboard Schematic Layer](http://localhost:4000/images/kb_schematic.png)