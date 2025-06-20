# 3D Recursive Line Sculpture Tool

A browser-based generative art tool for creating complex 3D sculptures using recursive algorithms. This application is built with vanilla JavaScript and leverages the power of Three.js for 3D rendering and interaction.

### [Live Demo](https://klmtseng.github.io/3D_Sculputure/)

## Features

This tool provides a highly interactive experience for crafting generative art with a wide range of controls:

* **Base Parameters**: Control the fundamental properties of the sculpture, including segment length, pivot ratio, and the total number of segments.
* **3D Motion Rules**: Define the recursive motion in 3D space with dedicated controls for Z-Axis displacement, as well as Roll, Pitch, and Yaw angles for complex rotations.
* **Visuals & Randomness**: Inject organic qualities into your creation by controlling the rate of hue change for vibrant color transitions and adding a degree of randomness to the rotation angles.
* **Helper Planes**: Toggle and customize the color of the XY, YZ, and XZ helper planes to better understand the sculpture's orientation in 3D space.
* **Interactive 3D Viewport**:
    * **Orbit**: Click and drag the left mouse button.
    * **Zoom**: Use the mouse scroll wheel.
    * **Pan**: Click and drag the right mouse button.
* **Parameter Export**: Instantly view the exact set of parameters that generate the current sculpture and copy them to your clipboard with a single click.

## How It Works: The Recursive Algorithm

The sculpture is not defined by a single closed-form equation but is generated iteratively. Each new segment's position and orientation is calculated based on the state of the previous one.

The core of the algorithm can be expressed with a recursive formula for the transformation matrix `C`:

$$
C_{i+1} = C_i \times \text{Translate}(D \times p_{ratio}, 0, zMove) \times \text{Rotate}(\text{pitch}, \text{yaw}, \text{roll})
$$

Where:
* `C_i` is the cumulative transformation matrix for segment `i`.
* `D` is the segment length.
* `p_ratio` is the pivot ratio.
* The rotation angles can be augmented with a random factor.

The final sculpture is the collection of all segments drawn according to their respective transformation matrices from `i = 0` to `n-1`.

## Technology Stack

* **HTML5**: Structure of the application.
* **Tailwind CSS**: For responsive and modern UI styling.
* **JavaScript (ES6+)**: For all the core logic, state management, and interaction.
* **Three.js**: For WebGL-based 3D rendering and camera controls.

## How to Use

1.  Clone this repository or download the files.
2.  Open the `index.html` file in any modern web browser.
3.  Start experimenting with the sliders to create your own unique sculptures!
