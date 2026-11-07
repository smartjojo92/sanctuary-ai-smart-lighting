# Local AI Integration – Home Assistant + Ollama

## Overview

This prototype integrates Home Assistant Assist with a locally hosted Qwen3 language model using Ollama.

The AI interprets natural-language requests, identifies exposed Home Assistant entities, and uses available Home Assistant tools to execute actions.

## Architecture

User → Home Assistant Assist → Ollama API → Qwen3 4B Instruct → Home Assistant Tools → Lighting Entities

## AI Environment

| Component | Configuration |
|---|---|
| Operating System | Windows 11 Home |
| Virtualization | Oracle VirtualBox |
| Automation Platform | Home Assistant OS |
| AI Runtime | Ollama |
| Language Model | qwen3:4b-instruct |
| GPU | NVIDIA GTX 1660 Ti 6 GB |
| Communication | Local HTTP API |
| Ollama Port | 11434 |

## Integration Setup

1. Install Ollama on the Windows host.
2. Download the Qwen3 4B Instruct model.
3. Configure Ollama to listen on an address reachable by Home Assistant.
4. Add the Ollama integration in Home Assistant.
5. Select Qwen3 4B Instruct as the conversation model.
6. Enable Home Assistant control through the conversation agent.
7. Expose the required lighting entities and scenes to Assist.

## Example API Check

```bash
curl http://127.0.0.1:11434/api/tags
```

This command checks whether Ollama is responding and lists the installed models.

## Demonstrated AI Commands

**Scene Selection**

"I'm going to watch a movie in the living room. Choose the appropriate lighting scene and activate it."

Observed result: Home Assistant activated the Movie Mode scene and adjusted the simulated living room lighting to 10%.

**Multiroom Control**

"Buddy, I'm leaving home. Turn off all the lights."

Observed result: The exposed bedroom and living room lights switched off.

**Bedtime Routine**

"Buddy, I'm going to bed. Please get my bedroom ready."

Observed result: The AI activated Sleep Mode, triggering the bedroom lighting automation.

## Engineering Notes

The lighting system uses simulated Home Assistant entities rather than physical controllers.

Lighting scenes and automation logic are handled by Home Assistant. The language model is responsible for interpreting requests and selecting appropriate actions.

The system is designed for local operation without requiring a cloud-hosted language model.

## Future Development

- Physical Philips Dynalite gateway integration
- Sensor-based automation
- HVAC and curtain control
- Improved AI response reliability
- Local voice input and output
- Building-wide lighting control
