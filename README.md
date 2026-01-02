# Unsloth for iOS (etLLM Demo)

This project demonstrates how to run LLMs natively on iOS devices using **ExecuTorch** and **Unsloth**. It provides a complete pipeline from model export (via Jupyter Notebooks) to on-device inference (via a native Swift app).

## 📱 Features

- **Native Performance**: Leverages XNNPACK, Core ML, or MPS backends for efficient on-device inference.
- **Support for Popular Models**: 
  - Gemma 3
  - LLaMA
  - LLaVA
  - Qwen 3
  - Phi 4
  - SmolLM 3
  - Voxtral
- **Memory Optimized**: Designed to handle the resource constraints of mobile devices.

## 📂 Project Structure

- **`/apple`**: The native iOS application built with SwiftUI and ExecuTorch.
  - Contains the `etLLM.xcodeproj`.
  - Includes UI for selecting models and chat interaction.
- **`/nb`**: Jupyter Notebooks for model preparation.
  - Tutorials for exporting models like Gemma 3 and Qwen 3 to the `.pte` format compatible with ExecuTorch.
- **`.gitignore`**: Configured for macOS and general development.

## 🚀 Getting Started

### 1. Export the Model
Navigate to the `nb/` directory and follow the notebooks to export your desired model:
- `gemma3-270m-export.ipynb`
- `Qwen3_(0_6B)-Phone_Deployment.ipynb`

This will generate a `.pte` model file and the corresponding tokenizer files.

### 2. Build the iOS App
Detailed instructions can be found in the [apple/README.md](./apple/README.md).

1. Open `apple/etLLM.xcodeproj` in Xcode 15.0+.
2. Ensure you have a development provisioning profile with the `increased-memory-limit` entitlement.
3. Build and run on your device or simulator.

### 3. Load Model and Chat
1. Copy the exported `.pte` and tokenizer files to your device's `etLLM` folder (via Files app or Finder).
2. Ensure files follow the naming convention (e.g., `llama...`, `qwen3...`) so the app can identify the architecture.
3. Select the files in the app and start chatting!

## 🛠 Requirements

- **Xcode 15.0** or later.
- **Mac** for development.
- **iOS Device** (recommended) with an Apple Silicon chip for best performance.

## 🔗 Credits & Documentation

- [Unsloth AI](https://github.com/unslothai/unsloth) - For incredible LLM optimization.
- [ExecuTorch](https://pytorch.org/executorch) - For the on-device inference engine.
- [Using ExecuTorch on iOS](https://docs.pytorch.org/executorch/1.0/using-executorch-ios.html)

---
*Created for the community to explore LLMs everywhere.*