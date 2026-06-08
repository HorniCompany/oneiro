# Scaleway Testing Plan (€100 Budget)

**Objective:** Use our €100 Scaleway credits to test the viability and latency of `vLLM` running `Gemma 4 12B Unified` (or a smaller variant) for real-time video/audio processing.

## 1. Instance Selection
- We need an instance with a GPU capable of running a 12B model in fp16 or 8-bit quantization.
- Look for instances with NVIDIA L4, A100, or H100 (if affordable), or multiple smaller GPUs (like 3090/4090 equivalents).
- **Budgeting:** €100 burns quickly on high-end GPUs. We must adopt a strict "Spin up, Test, Destroy" workflow. Do not leave instances running overnight.

## 2. Testing Phases

### Phase 1: Setup & Warmup (1-2 Hours)
- Provision a GPU instance (Ubuntu).
- Install Docker, NVIDIA Container Toolkit.
- Pull the `vLLM` nightly image that supports the encoder-free architecture (`vllm-openai:gemma4-unified`).
- Download `Gemma 4 12B` weights.

### Phase 2: Multimodal Latency Testing (2-4 Hours)
- Send a base64 encoded screenshot. Measure Time-to-First-Token (TTFT).
- Send a 5-second 16kHz `.wav` audio file. Measure TTFT.
- Send BOTH. Measure TTFT.
- **Target:** We need to know if the model can respond in under 500ms for a single `Action Token`.

### Phase 3: The "Raw Keystroke" Prompt Test (2 Hours)
- Feed the model screenshots of Minecraft.
- Prompt it to output strictly from a defined dictionary of Action Tokens (e.g., `{"cmd": "attack"}`).
- Test if it hallucinates text or consistently outputs the JSON/Token.

## 3. Teardown
- Ensure volumes and IPs are deleted to stop billing. Document all latency metrics in `/opt/Celestis/docs/testing/results.md`.