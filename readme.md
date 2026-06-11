# 2D Graphics Editor in C

A lightweight, console-based 2D graphics editor written in standard C. This application utilizes a 20x40 character array buffer as a text-based canvas, allowing users to draw, list, modify, and delete basic geometric shapes dynamically via an interactive command-line interface.

---

## Features

* **Interactive Canvas:** Generates and renders geometric shapes onto a matrix of 20x40 characters using `_` for empty space and `*` for filled pixels.
* **Supported Shapes:**
    * **Rectangle:** Solid rasterized rendering based on starting coordinates, height, and width.
    * **Line:** Implements the mathematically precise **Bresenham's Line Algorithm** to plot clean lines between any two points.
    * **Triangle:** Plots an empty, three-sided geometric structure by connecting three custom vertices.
    * **Circle:** Evaluates spatial distance bounds relative to a center point and a target radius.
* **Object Tracking System:** Assigns persistent unique tracking IDs to every active shape, enabling granular pipeline management.
* **Non-Destructive Editing:** Supports updating properties or deleting specific elements on-the-fly, which automatically updates and re-renders the underlying canvas.

---

## Architecture Overview

The program maintains separation between data management and visual output:

1.  **State Layer:** Active shapes are kept inside a global `objects` array structure, recording unique data parameters per enum type.
2.  **Raster Engine:** Invoking draw commands or a master redraw clears out the canvas and calculates structural pixel intersections.
3.  **Output Buffer:** Once rasterized, the matrix prints cleanly out to standard output via sequential console scans.

---

## Getting Started

### Prerequisites

You only need a standard C compiler (such as `gcc` or `clang`) installed on your operating system.

### Compilation

Compile the source code using the following terminal command:

```bash
gcc -o graphics_editor main.c -lm
