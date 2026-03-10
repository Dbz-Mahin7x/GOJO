## 🌀 SAT0RU – Jujutsu Kaisen Cursed Technique Visualizer

<div align="center">
<p align="center">
  <img src="https://files.catbox.moe/etx4xq.jpg" alt="Gojo Starou " width="100%" style="border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.3);">
</p>


https://img.shields.io/badge/Three.js-3D-0492C2?style=for-the-badge&logo=threedotjs&logoColor=white
https://img.shields.io/badge/Mediapipe-Hand%20Tracking-FF6B6B?style=for-the-badge&logo=google&logoColor=white
https://img.shields.io/badge/Theme-Jujutsu%20Kaisen-FF0000?style=for-the-badge&logo=anime&logoColor=white
https://img.shields.io/badge/Made%20with-💖-ff69b4?style=for-the-badge

✨ Unleash the power of Gojo Satoru's cursed techniques with your bare hands! ✨

</div>

---

🧿 About The Project

SAT0RU is an interactive cursed technique visualizer inspired by Gojo Satoru from the hit anime series Jujutsu Kaisen (呪術廻戦). Using real-time hand tracking and stunning 3D particle effects, this project lets you become the strongest sorcerer and perform iconic techniques with simple hand gestures.

The application combines Mediapipe's hand tracking with Three.js particle systems to create mesmerizing, volume-based visual effects that respond to your every move.

---

⚡ Cursed Techniques

<div align="center">

Technique Gesture Visual Effect
🔴 Cursed Technique Reversal: RED Left index finger up Blinding white-hot repulsive sphere
🔵 Cursed Technique Lapse: BLUE Right index finger up Gravitational attraction sphere
💜 Hollow Technique: PURPLE Both hands close together Chaotic singularity of red + blue
🌀 Domain Expansion: INFINITE VOID Cross fingers (either hand) Multi-layered celestial domain

</div>

---

🔮 Technique Details

🔴 Cursed Technique Reversal: RED

"A blinding white-hot core generating violent, jagged sphere of repulsive force."

Raise your left index finger to channel reversal energy. The red sphere materializes with:

· Bright white-hot core with red spiral arms
· Intense bloom effect and screen shake
· Counter-clockwise rotation

🔵 Cursed Technique Lapse: BLUE

"The power of attraction — an infinitely gathering mass of cursed energy."

Raise your right index finger to summon the blue sphere:

· Bright blue core with spiral arms
· Bloom and shake effects
· Clockwise rotation

💜 Hollow Technique: PURPLE

"Imaginary technique that erases everything in its path."

Bring both hands together (distance < 220px) to trigger the fusion sequence:

· Phase 1: Binary star orbit around common center
· Phase 2: Spiral pull toward each other
· Phase 3: Explosive collision
· Final: Majestic purple sphere with dual rotation

🌀 Domain Expansion: INFINITE VOID

"Throughout Heaven and Earth, I alone am the honored one."

Cross your index and middle fingers (either hand) to activate Gojo's ultimate technique:

· Phase 1 (Warp Speed): Particles fly horizontally at incredible speed
· Phase 2 (Black Hole): Multi-layered celestial domain featuring:
  · Bright accretion ring
  · Event horizon glow
  · Orbital debris
  · Deep cosmos background

---

🎮 How to Use

1. Allow camera access when prompted
2. Position yourself in good lighting with hands visible
3. Try these gestures:

Gesture Technique
☝️ Left index finger up 🔴 RED
☝️ Right index finger up 🔵 BLUE
✌️ Cross fingers (either hand) 🌀 INFINITE VOID
🤏 Both hands close together 💜 PURPLE (fusion sequence)
🖖 Index + ring + pinky up (3 fingers) ⚡ Charge projectile
👆 Any 3-finger gesture (charged) 💥 FIRE projectile at screen

---

🛠️ Tech Stack

Component Technology
3D Rendering Three.js (r160)
Hand Tracking Google Mediapipe
Post-Processing UnrealBloomPass
Styling CSS3 + Orbitron Font
Camera MediaPipe Camera Utils

---

🚀 Installation

Prerequisites

· Modern web browser (Chrome, Edge, Firefox recommended)
· Webcam
· JavaScript enabled

Local Setup

1. Clone the repository
   ```bash
   git clone https://github.com/Dbz-Mahin7x/sat0ru.git
   cd sat0ru
   ```
2. Add configuration file
   Create config.js in the same folder with your settings (see configuration section below)
3. Run the project
   · VS Code: Install "Live Server" extension, right-click index.html, select "Open with Live Server"
   · Direct: Open index.html in browser (may have CORS issues)

---

⚙️ Configuration

Create a config.js file with the following structure:

```javascript
// ============================================================
//  SAT0RU CONFIG — Adjust as you like, reload to see changes
// ============================================================

const CONFIG = {
    // Number of particles per sphere (higher = better visuals but more lag)
    BALL_COUNT: 10000,
    PARTICLE_BASE_SIZE: 0.3,

    // RED sphere (left hand)
    RED: {
        coreRatio: 0.12,
        coreRadius: 7,
        coreColor: { r: 3, g: 0.1, b: 0.1 },
        coreSize: 2.5,
        arms: 3,
        spiralSpeed: 15,
        spiralRadius: 30,
        spiralStartRadius: 2,
        spiralDepth: 8,
        armColor: { r: 0.8, g: 0, b: 0 },
        armSize: 1.0,
        rotationSpeed: -0.08,
        bloom: 2.5,
        shake: 0.25,
    },

    // BLUE sphere (right hand)
    BLUE: {
        coreRatio: 0.12,
        coreRadius: 7,
        coreColor: { r: 0.2, g: 0.6, b: 3.0 },
        coreSize: 2.5,
        arms: 3,
        spiralSpeed: 15,
        spiralRadius: 30,
        spiralStartRadius: 2,
        spiralDepth: 8,
        armColor: { r: 0, g: 0.2, b: 0.9 },
        armSize: 1.0,
        rotationSpeed: -0.08,
        bloom: 2.5,
        shake: 0.25,
    },

    // PURPLE (fusion)
    PURPLE: {
        coreRatio: 0.8,
        coreRadius: 12,
        coreColor: { r: 0.6, g: 0.5, b: 1.0 },
        coreSize: 1,
        outerSpread: 50,
        outerColor: { r: 0.5, g: 0.5, b: 0.7 },
        outerSize: 0.8,
        rotationSpeedA: 0.15,
        rotationSpeedB: -0.12,
        rotationY: 0.03,
        fusionDistance: 220,
        bloom: 1,
        shake: 1,
    },

    // FUSION animation
    FUSION: {
        orbitSpeed: 0.08,
        orbitStartRadius: 20,
        spiralShrinkRate: 0.97,
        spiralSpeedUp: 1.02,
        collisionRadius: 2,
        explosionDuration: 40,
        explosionScatter: 60,
        explosionBloom: 6.0,
        explosionShake: 1.5,
        reformSpeed: 0.08,
        orbitBloom: 3.5,
        orbitShake: 0.3,
    },

    // INFINITE VOID
    VOID: {
        ringRadius: 22,
        ringColor: { r: 1, g: 1, b: 1 },
        ringSize: 2.5,
        outerMinRadius: 25,
        outerMaxRadius: 95,
        outerColor: { r: 0.1, g: 0.6, b: 1.0 },
        outerSize: 0.7,
        rotationZ: 0.004,
        rotationX: 0.001,
        bloom: 3,
        shake: 0,
        posX: 0,
        posY: -5,
        posZ: 0,
        warpDuration: 60,
        warpSpeed: 10,
        warpBloom: 5.0,
        warpShake: 2.0,
    },

    // BLOOM post-processing
    BLOOM: {
        defaultStrength: 1.8,
        radius: 0.4,
        threshold: 0.85,
    },

    // Gesture detection
    DETECTION: {
        crossedFingerThreshold: 0.045,
        snapCooldownFrames: 30,
        chargeFrames: 20,
        minDetectionConfidence: 0.7,
        minTrackingConfidence: 0.6,
    },

    // Animation
    ANIMATION: {
        positionLerpSpeed: 0.5,
        morphLerpSpeed: 0.1,
        fadeInSpeed: 0.08,
        fadeOutSpeed: 0.04,
        shakeMultiplier: 12,
        neutralRotation: 0.005,
    },

    // Projectile (finger snap)
    PROJECTILE: {
        speed: 20,
        duration: 100,
        redDirection: { x: 1, y: 0.2, z: 1 },
        blueDirection: { x: -1, y: 0.2, z: 1 },
        purpleDirection: { x: 0, y: 0.2, z: 1 },
    },

    // Camera
    CAMERA: {
        width: 1280,
        height: 720,
        cameraZ: 55,
        fov: 75,
    },

    // Debug
    DEBUG: {
        showLandmarks: true,
    },
};

export default CONFIG;
```

---

📁 Project Structure

```
sat0ru/
├── 📄 index.html          # Main application
├── 📄 config.js           # Configuration file (you create this)
└── 📄 README.md           # You are here!
```

---

🎨 Visual Effects

Effect Description
Bloom Intense glow using UnrealBloomPass
Screen Shake Camera vibration during techniques
Particle Morphing Smooth transitions between shapes
Spiral Arms Rotating particle streams
Warp Speed Horizontal particle streaks for Void intro
Fusion Sequence 3-phase animation (orbit → spiral → explosion → purple)
Hand Tracking Real-time skeleton overlay (toggle with DEBUG.showLandmarks)

---

📝 Notes

· This project was built with inspiration from Jujutsu Kaisen by Gege Akutami
· The name SAT0RU is a tribute to Gojo Satoru
· All particle effects are generated procedurally using Three.js
· Hand tracking powered by Google Mediapipe

---

🤝 Contributing

Contributions are welcome! Feel free to:

· 🍴 Fork the repository
· 🌿 Create a feature branch
· 💾 Commit your changes
· 📤 Push to the branch
· 🔁 Open a Pull Request

---

📜 License

Distributed under the MIT License. See LICENSE for more information.

---

💖 Author

Mahin Ahmed (Rentaro Aijo)

<div align="center">

<a href="https://www.facebook.com/RentaroAijo.4x">
  <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" />
</a>
<a href="https://github.com/Dbz-Mahin7x">
  <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" />
</a>
<a href="https://instagram.com/dbz_mahin">
  <img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" />
</a>

16 years old • From The Future • Code with Love 💕

</div>

---

🙏 Acknowledgments

· Gege Akutami – Creator of Jujutsu Kaisen
· Three.js Team – Amazing 3D library
· Mediapipe Team – Hand tracking technology
· Google Gemini 3 – AI-powered code assistance

---

<div align="center">

🎀 "Throughout Heaven and Earth, I alone am the honored one." 🎀

<br>

<img src="https://profile-counter.glitch.me/sat0ru-visualizer/count.svg" alt="Visitor Count" />

<br>

© 2026 Mahin Ahmed. All rights reserved.

</div>
