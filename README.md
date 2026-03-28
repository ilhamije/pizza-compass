# Pizza Compass 🍕

A minimalist, high-end web tool that acts as a magical compass, guiding you directly to the perfect slice of pizza.

## 🚀 How It Works

This application is a single-file Progressive Web Tool that leverages modern browser APIs to create an immersive, sensor-driven experience:

1.  **Geolocation Tracking**: Uses the `navigator.geolocation` API to track your real-time coordinates. It calculates the **Haversine distance** (air distance) between your current position and the fixed target (Adiba Pizza).
2.  **Dynamic Bearing**: It calculates the mathematical bearing from your location to the target. By combining this with the `deviceorientation` (magnetometer) or GPS heading, the pizza "needle" rotates to point exactly where you need to go.
3.  **Pedometer (Step Detection)**: Tracks your movement using the `devicemotion` API. It applies a **Low-Pass Filter** to gravity data and detects spikes in acceleration to count steps, providing haptic-like visual feedback on every step.
4.  **Premium UI/UX**: Built with vanilla CSS, focusing on a dark, high-contrast aesthetic with "glassmorphism" elements, custom SVG graphics, and smooth "Lerp" (Linear Interpolation) animations for the compass needle.

---

## 📝 The Build Prompts

Here are the prompts used to generate this application, ranging from the initial vision to the final polish.

### 1. The Core Concept (Initial Prompt)
> "Create a minimalist, premium-looking web app called 'Pizza Compass'. It should be a single `index.html` file. The goal is to point users toward a specific pizza location (Adiba Pizza at `TARGET_LAT`, `TARGET_LNG`).
> 
> Features:
> - A central compass needle that is a stylized SVG pizza slice.
> - The pizza slice should always point toward the target coordinates.
> - Use the Geolocation API for distance and the Device Orientation API for heading.
> - Include a step counter that uses the accelerometer to detect walking.
> - The design must be extremely premium: dark mode, deep oranges/golds, Inter font, and smooth rotations.
> - Handle iOS permission requests for motion and orientation sensors."

### 2. Refining the Pedometer Logic
> "The step counter is too sensitive/not sensitive enough. Improve it by implementing a low-pass filter to isolate gravity from user acceleration. Use a threshold-based peak detection with a 350ms debounce to prevent double-counting. Also, add a visual 'pulse' animation to the UI every time a step is detected."

### 3. Smoothing the Needle 
> "The compass needle is currently jittery because of sensor noise. Implement a requestAnimationFrame loop with a 'Lerp' (Linear Interpolation) function to make the needle rotation fluid and organic, rather than snapping to angles."

### 4. Final Polish and SEO
> "Add a 'Buy Me Coffee' button at the bottom linking to my Sociabuzz profile. Ensure the app is responsive on all mobile screens and add SEO meta tags. Make the 'Permission' screen look like a high-end splash screen with the title 'ADIBA PIZZA' in big, bold, gold letters."

---

## 🛠️ Tech Stack
- **Languages**: HTML5, CSS3 (Vanilla), JavaScript (ES6+)
- **APIs**: Geolocation, DeviceOrientation, DeviceMotion
- **Typography**: Inter (Google Fonts)
- **Deployment**: Any static host (GitHub Pages, Vercel, Netlify)
