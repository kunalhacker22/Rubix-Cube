# 🧊 3D Rubik's Cube

## Project Name: 3D Rubik's Cube

A fully interactive, web-based simulation of a standard 3x3x3 Rubik's Cube. It utilizes pure HTML, CSS 3D transforms, and JavaScript for complex layer rotation logic, allowing users to scramble and solve the cube directly in their browser.

## ✨ Features

* **Interactive 3D View:** The cube is rendered in 3D using CSS `transform-style: preserve-3d` and `transform: rotateX/rotateY`.
* **Mouse/Touch Interaction:**
    * **Cube Rotation:** Click and drag anywhere on the cube or the surrounding area to rotate the entire cube's perspective.
    * **Layer Twisting:** Click and drag one of the smaller cubelets to initiate a **layer twist** (e.g., rotating the top face, the front face, or the middle slice).
* **Smooth Animations:** Utilizes CSS transitions for smooth, satisfying rotation animations for both the overall cube movement and the layer twists.
* **Scrambling and Reset:** Although not explicitly shown in the minimal code, the structure is ready for the implementation of scramble/solve/reset functionalities typical of a Rubik's Cube simulator.

## 🛠️ Technology Stack

* **HTML (`index.html`):** Defines the structure, including the main `.cube` container and the individual faces and stickers.
* **CSS (`style.css`):** Handles all visual styling, layout, the 3D projection, and the complex `transform` properties that define the 3D space and positions of the 26 outer cubelets.
* **JavaScript (`script.js`):** Contains the core logic for user input detection (mouse/touch), calculating which layer should rotate based on the drag direction, and applying the correct CSS transforms to groups of cubelets for a layer twist.

## 🚀 Getting Started

1.  **Clone the Repository:**
    ```bash
    git clone [Your Repository URL]
    ```
2.  **Open the File:**
    Open the `index.html` file directly in your modern web browser.

### Usage

1.  **Rotate the Cube:** Click and drag outside of the cube's faces to change the viewing angle.
2.  **Twist a Layer:** Click and drag a face of one of the smaller cubelets in a perpendicular direction (e.g., dragging the top face horizontally or the right face vertically) to twist that layer.

## ⚙️ Key Logic Breakdown (The Maths of the Cube)

The JavaScript (`script.js`) is responsible for managing the state and performing the complex rotational calculations:

### 1. State Management

The script likely maintains a 3D array or similar structure to track the position and orientation of the 26 movable outer cubelets (cubies).

### 2. Event Handling and Drag Logic

* **`mousedown`/`touchstart`:** Records the initial cursor position.
* **`mousemove`/`touchmove`:** Calculates the change in position ($\Delta x$ and $\Delta y$) to determine if the user is performing a whole-cube rotation or a layer twist.
* **Layer Identification:** When a drag starts on a cubelet, the script uses the cubelet's current 3D position to determine which face the user is interacting with (e.g., Top, Front, Right).

### 3. Layer Twist Logic (The Hard Part)

When a layer twist is detected, the script must:

* **Identify the Cubies:** Select the 9 cubelets that belong to the layer being rotated (e.g., the 9 cubies on the "Front" face).
* **Apply CSS Transform:** Temporarily group those 9 elements and apply a **single CSS `transform: rotateZ/rotateY/rotateX(90deg)`** to the group to create the illusion of a single twist.
* **Update State:** Once the animation is complete, the script updates the internal state of those 9 cubies (their position and color orientation) to reflect the new solved/scrambled state.

## 📸 Screenshots

*(Add a screenshot or GIF of your interactive cube here)*
