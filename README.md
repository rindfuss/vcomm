# VT-100 Terminal Emulator in 8088 Assembly code

## Background
This code comes from *way* back in the archives from the MS-DOS, command line days. The program provided an interface to the serial port of a IBM PC-compatible computer, transmitting characters typed and displaying characters received. In addition it interpreted part of the VT-100 terminal protocol that specified special escape sequences that told the receiving terminal to do things like move the cursor around on the screen, change character attributes like highlight and blink, and - if memory serves - even divide the screen into sections.

## Features
- Basic VT100 terminal emulation.
- Support for a command mode similar to typing a colon in VI. User could issue commands that included turning off terminal emulation so incoming data was simply displayed with no interpretation, setting the com port to use, setting the baud rate, exiting the program, and the code indicates planned future support for turning on a feature so that the incoming data would be echoed to a printer as it was being displayed on the screen.

## Code Highlights
- The program is basically a loop that transmits any characters that have been typed, polls to see if a character has been received, and if a character has been received goes through the equivalent of a long series of nested if-then-else statements to see what the received character is and take appropriate action, either displaying the character or interpreting an escape sequence.
- Interacting with the screen and serial port is done via BIOS interrupts.

> Written with [StackEdit](https://stackedit.io/).