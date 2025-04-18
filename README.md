# Interactive 2D Terrain Generator

This is a simple, interactive 2D terrain generator built with HTML, CSS, and JavaScript. It uses Perlin noise and Fractional Brownian Motion (FBM) to create tile-based terrain maps that can be explored and customized in real-time.

## Features

*   **Perlin Noise:** Generates smooth, natural-looking noise patterns.
*   **Fractal Noise (FBM):** Combines multiple layers (octaves) of Perlin noise for more detailed and complex terrain features.
*   **Customizable Parameters:** Adjust noise scale, octaves, persistence, lacunarity, height scale, sea level, and tile size via a sidebar UI.
*   **Color Presets:** Includes several predefined color palettes and parameter sets (e.g., Earth, Mars, Islands, Volcanic, B&W).
*   **Interactive Panning:** Explore the generated world using mouse drag or keyboard controls (WASD/Arrow Keys).
*   **Grid Overlay:** Toggleable grid lines to visualize the tile structure.
*   **Seed Regeneration:** Generate entirely new terrain maps with a button press (or 'R' key).
*   **Responsive:** Adapts to different screen sizes.
*   **Collapsible Sidebar:** Hide the controls for an unobstructed view.
*   **High-DPI Support:** Renders crisply on high-resolution displays.

## How to Use

1.  **Download:** Clone this repository or download the `terrain_generator.html` file.
2.  **Open:** Open the `terrain_generator.html` file directly in your web browser (Chrome, Firefox, Edge, Safari recommended).
3.  **Interact:**
    *   **Pan:** Click and drag the terrain map with the mouse, or use the `W`, `A`, `S`, `D` or Arrow keys.
    *   **Customize:** Use the controls in the sidebar on the left to change parameters like tile size, noise settings, and sea level. The terrain will update automatically.
    *   **Presets:** Select a pre-configured theme from the "Preset" dropdown.
    *   **New World:** Click the "Generate New Seed" button or press the `R` key to generate a completely new map with the current settings.
    *   **Toggle Grid:** Check/uncheck the "Show Grid Lines" box.
    *   **Toggle Sidebar:** Click the arrow button (`⮜`/`⮞`) in the top-right corner of the sidebar to collapse or expand it.

## Technology Stack

*   **HTML:** Structure of the page and controls.
*   **CSS:** Styling for the layout, sidebar, controls, and canvas. Uses CSS Variables and Transitions.
*   **JavaScript (Vanilla):**
    *   Handles all logic for noise generation, rendering, UI interaction, and event handling.
    *   Uses the `<canvas>` element for rendering.
    *   Implements Perlin noise and FBM algorithms from scratch.

## Code Structure (JavaScript)

*   **`Perlin` Class:**
    *   Implements the core Perlin noise algorithm.
    *   Includes methods for generating pseudo-random numbers, gradient vectors, fading, and calculating noise values at 2D points.
    *   Uses a simple XORShift PRNG and caches gradients.
*   **`Terrain` Class:**
    *   The main application class.
    *   Manages the canvas, rendering context, and high-DPI scaling.
    *   Stores application state (parameters, view offset, keyboard/mouse state).
    *   Initializes the UI, binds event listeners (controls, mouse, keyboard, resize).
    *   Handles preset loading and application.
    *   Implements the `fractal` method for FBM using the `Perlin` class.
    *   Contains the `getColor` logic based on noise value and defined color ranges/palettes.
    *   Includes the main `loop` (using `requestAnimationFrame`) and `render` methods.
*   **Global Scope:** An event listener initializes the `Terrain` class instance when the window loads.

## Potential Extensions

*   Add more complex terrain features (rivers, erosion simulation).
*   Implement different noise algorithms (Simplex, Worley).
*   Add saving/loading of custom presets or map seeds.
*   Introduce basic lighting or shading effects.
*   Optimize rendering for extremely large maps (e.g., drawing only visible chunks).

## License

This project is open source. Feel free to use, modify, and distribute it. (Consider adding a specific license like MIT if desired).
