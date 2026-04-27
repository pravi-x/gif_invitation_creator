# 🎉 GIF Invitation Creator

Turn two JPG images into an animated GIF invitation with a stylish transition effect. Built to run in Google Colab — no local setup needed.

---

## How it works

1. Upload **Image 1** — your hero/background image
2. Upload **Image 2** — your event details (date, time, venue, etc.)
3. Choose a transition effect
4. Export and download your animated GIF

---

## Getting started

1. Open `gif_invitation_creator.ipynb` in [Google Colab](https://colab.research.google.com)
2. Run all cells top to bottom (**Runtime → Run all**)
3. Upload your two JPGs when prompted
4. Download the finished `invitation.gif`

---

## Configuration

All settings live in the **Step 2 — Config** cell:

| Parameter | Default | Description |
|---|---|---|
| `OUTPUT_SIZE` | `(800, 600)` | Output dimensions in pixels |
| `HOLD_FRAMES_1` | `40` | Frames Image 1 stays on screen |
| `IMG2_SECONDS` | `15` | Seconds Image 2 stays on screen |
| `FRAME_DELAY` | `60` | Milliseconds per transition frame |
| `TRANSITION` | `glitter_wipe` | Transition effect (see below) |
| `TRANS_FRAMES` | `30` | Number of frames in the transition |
| `LOOP_COUNT` | `0` | `0` = loop forever, `1` = play once |
| `OUTPUT_FILE` | `invitation.gif` | Output filename |

---

## Transition effects

| Name | Description |
|---|---|
| `glitter_wipe` ⭐ | Diagonal sweep with gold & white sparkles |
| `crossfade` | Smooth alpha blend between images |
| `slide_left` | Image 1 slides out, Image 2 slides in |
| `zoom_blur` | Zoom + gaussian blur through black |
| `sparkle_fade` | Random pixel dissolve with sparkle boundary |
| `shatter` | Image 1 breaks into tiles that fly away |

To switch transition, edit the `TRANSITION` variable in the config cell:

```python
TRANSITION = 'shatter'
```

---

## Tips

- **Image 2 read time** — set `IMG2_SECONDS = 15` (or more) so guests have time to read event details
- **Image quality** — higher resolution inputs produce larger GIF files; `(800, 600)` is a good balance
- **Loop once** — set `LOOP_COUNT = 1` if you don't want the GIF to loop
- **Transition speed** — lower `TRANS_FRAMES` = faster transition, higher = slower and smoother

---

## Requirements

Handled automatically by Colab:

- `Pillow` — image processing and GIF export
- `imageio` — image I/O utilities
- `numpy` — pixel-level frame compositing

---

## Output

A single `invitation.gif` file, downloaded automatically after generation. Preview renders inline in the notebook before download.
