# Hackathon Strategy & Resources

## 1. The Team (lablab.ai)
**Goal:** Recruit a 3rd or 4th member from the lablab.ai community to complement our skills.
**Ideal Candidate Profile:**
- Deep understanding of C++ and OS-level APIs (X11/Wayland on Linux, WinAPI on Windows) for the screen capture and keystroke injection.
- OR a prompt engineering wizard who knows how to format multimodal inputs for `Gemma 4` to minimize hallucinations.
- **Pitch:** "We are building an open-source General Embodied Agent framework (C++/TS) that bypasses game APIs and plays using raw screen capture and keystrokes. Backed by Scaleway credits for testing. Need low-level C++ devs or VLA prompt experts."

## 2. The AI Coding Assistant Problem ("Vibecoding")
**The Issue:** We need unlimited or high-limit access to a top-tier coding LLM (like Claude 3.5 Sonnet or Opus) during the 48-72 hours of the hackathon. We cannot afford rate limits when writing complex C++ <-> TS bridges.
**Potential Solutions:**
1. **API Funding:** Seek micro-grants or pool funds to pre-load an Anthropic/OpenAI API account. Using the API via an interface (like Cursor or custom tools) often bypasses the strict message limits of the web UI.
2. **Hackathon Perks:** Check if the AMD/lablab.ai hackathon provides free API credits to participants (they often partner with AI providers).
3. **Multiple Accounts:** The classic (though less elegant) solution of pooling resources across team members' subscriptions.

## 3. Pre-Hackathon Deliverables (No Code)
Before the timer starts, we must have:
- [ ] Complete architectural diagrams (PlantUML or Mermaid).
- [ ] API schemas defined (How TS talks to C++).
- [ ] `vLLM` tested on Scaleway to confirm inference latency.
- [ ] Prompts drafted for the VLA model.