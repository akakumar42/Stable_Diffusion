# 🚀 Stable Diffusion From Scratch (PyTorch)

A **from-scratch implementation of a Latent Diffusion Model** using PyTorch.  
This project rebuilds the core ideas behind modern text-to-image systems like Stable Diffusion, focusing on **understanding internals rather than using black-box APIs**.

---

# 🧠 Project Overview

This project implements a complete **text → image generation pipeline**, including:

- Text encoding using CLIP
- Latent space diffusion (DDPM)
- UNet with attention mechanisms
- Classifier-Free Guidance (CFG)
- VAE encoder & decoder

Pipeline flow:

Text Prompt → Tokenization → CLIP Embedding → Latent Noise → Diffusion → Image

---

# ⚙️ Features

## 🔹 Text-to-Image Generation
- Generate images from natural language prompts
- Supports conditional and unconditional prompts

## 🔹 Diffusion Model (DDPM)
- Forward and reverse diffusion process
- Custom sampler implementation

## 🔹 Classifier-Free Guidance (CFG)
Improves generation quality:

    output = cfg_scale * (cond - uncond) + uncond

## 🔹 Latent Space Optimization
- Works in compressed latent space (efficient)
- Faster than pixel-space diffusion

## 🔹 UNet Architecture
- Residual blocks
- Self-attention + cross-attention
- Time embeddings

---

# 📂 Project Structure

.
├── pipeline.py        # End-to-end generation pipeline  
├── diffusion.py       # UNet + diffusion model  
├── encoder.py         # VAE encoder  
├── decoder.py         # VAE decoder  
├── attention.py       # Attention layers  
├── ddpm.py            # Diffusion sampler  
├── model_loader.py    # Model loading utilities  

---

# 🔁 Core Pipeline

## Step 1: Encode Text
- Tokenize input prompt
- Generate embeddings using CLIP

## Step 2: Initialize Latents
- Random noise OR encoded input image

## Step 3: Denoising Loop
- Predict noise using UNet
- Update latents iteratively

## Step 4: Decode Image
- Convert latent → RGB image using VAE decoder

---

# 🧪 Example Usage

```python
image = generate(
    prompt="A futuristic city at sunset, ultra detailed",
    uncond_prompt="",
    cfg_scale=7.5,
    n_inference_steps=50,
    device="cuda"
)
```

---

# 🧠 Concepts Covered

- Diffusion Probabilistic Models (DDPM)
- UNet Architecture
- Attention Mechanisms (Self + Cross)
- Time Embeddings
- Latent Space Representation
- Classifier-Free Guidance

---

# 🚀 What I Learned

- How modern text-to-image systems work internally
- How diffusion models are trained and sampled
- Importance of latent space optimization
- Practical implementation of attention mechanisms
- Debugging large deep learning systems

---

# 🙌 Credits & Inspiration

This project is inspired by:

- Umar Jamil’s deep learning and diffusion model explanations
- Open-source diffusion implementations from the community
- A GitHub repository used for **model weight conversion utilities**

I adapted ideas and concepts while implementing everything from scratch to deepen my understanding.

---

# 🛠️ Tech Stack

- Python 3.11+
- PyTorch
- NumPy
- tqdm

---

# 📌 Future Improvements

- Add DDIM sampler
- FP16 / mixed precision optimization
- Web UI (Gradio / Streamlit)
- Fine-tuning support (LoRA, DreamBooth)

---

# ⭐ If you like this project, consider starring the repo!

---

# 👨‍💻 Author

Akash Kumar
