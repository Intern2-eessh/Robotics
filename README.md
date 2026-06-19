# ELAMANITECH | Futuristic 3D Robotics Website

A highly immersive, interactive 3D landing page for next-generation robotics built using **Three.js** and **GSAP**.

## Features

1.  **Cinematic Intro Sequence (GSAP Timeline)**:
    *   **Phase 1 (Entrance)**: The robot spawns in the distance and runs forward toward the camera playing a dynamic "Run" animation.
    *   **Phase 2 (Climax)**: The robot executes an athletic "Somersault" jump in the center of the viewport, landing with a camera-shake effect.
    *   **Phase 3 (Split-Screen Transition)**: The robot lands and transitions to a confidently standing "Pose" animation while shifting to the Left-Hand Side (LHS) of the screen.
    *   **Phase 4 (UI Reveal)**: A sleek semi-transparent glassmorphic specifications card slides in on the Right-Hand Side (RHS), accompanied by simulated terminal boot logs.
2.  **High-Fidelity Procedural Orange Robot**:
    *   Designed procedurally in pure Three.js to match your uploaded reference image.
    *   Includes a glossy orange shell, inner carbon fiber spinal core, silver hydraulic joint connectors, ear antennas, and a custom CRT-helmet head.
    *   **Expressive Digital Eyes**: A dynamic canvas face texture displaying blinking smiling arch eyes (just like the reference image) that blink every 3.5 to 7 seconds.
3.  **Rigged GLTF Loader (`robot.glb`)**:
    *   The app checks for an external `robot.glb` file. If present, it swaps out the procedural model and automatically maps standard skeletal mesh nodes (Head, Torso, Arms, Legs) for mouse interaction.
    *   It extracts and blends four standard animations: `"Run"`, `"Somersault"`, `"Idle"`, and `"Pose"` using `THREE.AnimationMixer` to hook into the GSAP timeline.
4.  **Raycaster Body Part Inspection**:
    *   Once the intro sequence finishes, mouse interactions are enabled.
    *   Hovering your cursor over different body parts (Head, Torso, Left Arm, Right Arm, Legs) lights them up with a glowing neon cyan emissive color.
    *   A floating 2D HTML tooltip follows the cursor, detailing diagnostic specs for the hovered part.
    *   Moving the cursor away resets the highlights and fades out the tooltip.
5.  **Reflective Ambient Environment**:
    *   A dark cyber-grid floor paired with a dark metallic plane receives shadows, providing depth and scale.
    *   Dual neon-spotlights (Cyan and Magenta) generate beautiful rim-light and silhouette contours on the robot.

## Getting Started

### Prerequisites

To run this project, you need a local web server because browsers restrict loading ES6 modules (like `app.js`) directly from local files (`file://` protocol) due to security policies.

### Run Local Server

You can run a local server using any of the following methods:

#### Method A: Python (Easiest, no installation needed if you have Python)
Open your terminal in this project folder and run:
*   **Python 3**: `python -m http.server 8000`
*   **Python 2**: `python -m SimpleHTTPServer 8000`

Then open [http://localhost:8000](http://localhost:8000) in your browser.

#### Method B: VS Code Extension
If you are using Visual Studio Code:
1.  Install the **Live Server** extension.
2.  Right-click `index.html` and select **Open with Live Server**.

#### Method C: Node.js (If Node is installed)
Run:
```bash
npm install
npm run dev
```

---

## Adding Your Own GLTF Model

To load your own rigged model:
1.  Save your 3D model as `robot.glb` in this root directory.
2.  Ensure it contains rigged animation clips named exactly `"Run"`, `"Somersault"`, `"Idle"`, and `"Pose"`.
3.  Ensure the inner mesh elements contain standard keywords in their names (e.g. `'head'`, `'torso'`, `'left'`, `'right'`, `'arm'`, `'leg'`) so the automatic raycaster tagging maps the correct tooltips.
