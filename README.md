# ⚙️ ffmpeg-mysofa-builder

This repository contains an automated **GitHub Actions** workflow to cross-compile a custom `libffmpeg.so` shared library for Android, bundled with **`libmysofa`**.

Built specifically to offload heavy NDK compilation to the cloud from a modest Android device, providing the core spatial audio engine (`sofalizer` filter) used in my other projects like [My-SofaLizeR](https://github.com/WinterFarmer/My-SofaLizeR).

---

## ✨ What This Builds

- **Target Output:** `libffmpeg.so` for Android (ARM64 / `arm64-v8a`).
- **Bundled Library:** [libmysofa](https://github.com/hoene/libmysofa) compiled and statically/dynamically linked into FFmpeg.
- **Key Feature Enabled:** FFmpeg `sofalizer` audio filter (`--enable-libmysofa`) for rendering multichannel audio into binaural 3D stereo using `.sofa` HRTF datasets.

---

## 🚀 How It Works

1. **Automated Cloud Build:** Every workflow run triggers an Ubuntu runner via GitHub Actions.
2. **NDK Cross-Compilation:** Downloads the Android NDK, compiles `libmysofa`, and builds FFmpeg with custom flags optimized for audio/video processing.
3. **Artifact / Release Output:** Produces a ready-to-use `libffmpeg.so` binary without needing a local PC or heavy device resources.

---

## 📥 Download Pre-built `libffmpeg.so`

You don't need to run the workflow yourself if you just need the compiled binary. Grab the pre-built `libffmpeg.so` directly from the Releases page:

👉 **[Download `libffmpeg.so` from Releases](../../releases)**

---

## 🔗 Related Projects

- **[My-SofaLizeR](https://github.com/WinterFarmer/My-SofaLizeR):** Android app that uses this custom build to convert multichannel `.mkv` files into binaural stereo surround + AutoEQ.
- **[mpv-android-custom](https://github.com/WinterFarmer/mpv-android-custom):** Custom `mpv-android` fork with `libmysofa` bundled for real-time `sofalizer` playback.
  
