# SimpleChatbot Setup Guide

## System Requirements

| Requirement | Details |
|-------------|---------|
| Python | 3.8 or higher |
| RAM | Minimum 8 GB (16 GB recommended) |
| Disk Space | At least 5 GB free |
| OS | Windows 10/11, macOS 10.15+, or Linux |
| Internet | Required only for the initial model download |
| GPU | Optional — NVIDIA CUDA speeds things up, but CPU works fine |

> **No GPU? No problem.** The script automatically falls back to CPU. Responses will take 1–3 minutes per reply but will work correctly.

---

## Installation

### Step 1 — Check your Python version

```bash
python --version
```

You need Python 3.8 or higher. Download from [python.org](https://python.org) if needed.

### Step 2 — Install dependencies

```bash
pip install torch
pip install transformers==4.40.2
```

> **Important:** Pin `transformers` to `4.40.2`. Newer versions (5.x) have a breaking incompatibility with Phi-3 Mini's `rope_scaling` config that causes a `KeyError: 'type'` crash on startup.

### Step 3 — Save the script

Save `simplechatbot.py` to a folder of your choice, for example your Desktop or a folder named `workshop`.

---

## Running the Chatbot

### Launch the script

```bash
python simplechatbot.py
```

### What happens on first run

| Step | What's happening |
|------|-----------------|
| 1 | Model files download from Hugging Face (~3.8 GB, one time only) |
| 2 | Model loads into RAM — takes 20–60 seconds |
| 3 | `You:` prompt appears — type your message and press Enter |
| 4 | Response is generated — 1–3 min on CPU, ~10 sec on GPU |

### Exiting

Type `x` and press Enter at any time:

```
You: x
Goodbye!
```

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| `KeyError: 'type'` on startup | Run `pip install transformers==4.40.2` and try again |
| `ModuleNotFoundError: transformers` | Run `pip install transformers==4.40.2` |
| `ModuleNotFoundError: torch` | Run `pip install torch` |
| Model loads but no response prints | Make sure you are running the latest version of the script |
| Out of memory / process killed | Close other apps. 8 GB RAM minimum required. |
| Download is very slow | The model is ~3.8 GB. It only downloads once — subsequent runs load from disk. |
| Response takes 1–3 minutes | Normal on CPU. A GPU will reduce this to under 10 seconds. |

---

## Quick Reference

**Install:**
```bash
pip install torch
pip install transformers==4.40.2
```

**Run:**
```bash
python simplechatbot.py
```

**Exit:** type `x` and press Enter
