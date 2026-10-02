# 🎞️ Manga Motion Optimization Pipeline

A simple workflow for turning manga panels into motion videos with **CapCut**, then encoding them with **HandBrake** so they hold up against social media compression.

---

## 🖼️ Tutorial Posters

![Manga Motion Tutorial Poster - main workflow guide](assets/Manga%20Motion%20Tutorial%20Poster.png)

![Manga Motion Tutorial Poster 2 - supplementary guide](assets/Manga%20Motion%20Tutorial%20Poster%20%281%29.png)

---

## 🔄 Pipeline

```mermaid
graph LR
    A[Raw Manga Panels] --> B[CapCut Editing]
    B --> C[Raw Render]
    C --> D[HandBrake Transcoder]
    D --> E[Social Media Upload]
```

---

## 🧰 Toolstack

```mermaid
mindmap
  root((Toolstack))
    CapCut Desktop
      Color correction
      Masks and layering
      Keyframes
      Raw export
    HandBrake
      Constant FPS
      H.264 encode
      Bitrate cap
    AI Clarity Tools
      Upscaling
      Sharpening
```

---

## ✂️ CapCut Editing Steps

```mermaid
flowchart TD
    A[Import Panels] --> B[Color Correction]
    B --> C[Background Layering]
    C --> D[Feathered Masks]
    D --> E[Keyframing: zoom and pan]
    E --> F[Add Audio]
    F --> G[Export Raw Render]
```

1. **Color correction:** keep blacks deep and line art crisp.
2. **Background layering:** put a blurred or tinted backdrop behind each panel to avoid black bars.
3. **Feathered masks:** soften panel edges so they blend into the background.
4. **Keyframing:** animate scale and position for smooth pans and zooms.
5. **Export:** render a high-quality raw file.

---

## ⚙️ HandBrake Encoding

A ready-made preset is included: [`preset/handbrake_manga_motion.json`](preset/handbrake_manga_motion.json)

**To use it:** open HandBrake → **Presets** → **Import** → select the JSON file → load your raw render → **Start Encode**.

```mermaid
sequenceDiagram
    participant R as Raw Render
    participant H as HandBrake
    participant P as Social Platform
    R->>H: High-bitrate video
    H->>H: Constant FPS, RF 20-22, 12-15 Mbps cap
    H->>P: Optimized MP4
    P->>P: Re-encodes with less damage
```

### Settings

| Setting | Value |
|---------|-------|
| Container | MP4 |
| Video Codec | H.264 |
| Framerate | Constant (match source, e.g. 30 or 60) |
| Quality (RF) | 20 to 22 |
| Bitrate Cap | 12 to 15 Mbps |
| Audio | AAC |

---

## 🛠️ Troubleshooting

```mermaid
graph TD
    A[Problem] --> B[Pixelation]
    A --> C[Audio Desync]
    A --> D[Black Bars]
    B --> B1[Lower RF to 20 and raise bitrate cap]
    C --> C1[Use Constant Framerate in HandBrake]
    D --> D1[Match canvas ratio and add a background layer]
```

---

## 📁 Repository Structure

```text
manga-motion-optimization-pipeline/
├── assets/
│   ├── Manga Motion Tutorial Poster.png
│   └── Manga Motion Tutorial Poster (1).png
├── preset/
│   └── handbrake_manga_motion.json
└── README.md
```

---

## 📜 Credits

- **Manga:** *Blood on the Tracks* by **Shuzo Oshimi**. All rights belong to the author and publishers.
- **Tools:** [CapCut](https://www.capcut.com/) and [HandBrake](https://handbrake.fr/).

This project is for educational purposes only and is not affiliated with the original author or publishers. Please support the official release.
