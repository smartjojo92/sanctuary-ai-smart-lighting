# Sanctuary AI – Smart Lighting Prototype

**Local AI-Powered Smart Home Automation | Home Assistant + Ollama + Qwen3**

A working software proof of concept demonstrating how a locally hosted AI model can interpret natural-language commands and control simulated smart lighting through Home Assistant.

**Developed by:** Jojo Jose  
**Designation:** Manager – Controls & Automation

## Project Overview

This project explores the integration of artificial intelligence with residential lighting automation.

The objective is to demonstrate how conversational AI can simplify everyday interactions with smart home systems, including lighting dimming, scene selection, bedtime routines, and multiroom control.

The prototype combines Home Assistant's automation capabilities with a locally hosted Qwen3 language model through Ollama.

## System Architecture

```text
User's Natural-Language Command
              |
              v
     Home Assistant Assist
              |
              v
      Ollama Local API
       Qwen3 4B Instruct
              |
              v
   Home Assistant Actions
              |
              v
 Virtual Lighting and Scenes
```

The AI interprets the user's request and selects appropriate Home Assistant actions. Home Assistant handles the actual entity control and automation logic.

## Working Demonstrations

| Demonstration | Command / Action | Result |
|---|---|---|
| AI Lighting Dimming | Set living room lighting to 50% | Virtual dimmer adjusts to 50% |
| Movie Mode | Activate living room Movie Mode | Predefined scene sets lighting to 10% |
| Bedtime Automation | "Buddy, I'm going to bed" | Sleep Mode activates and bedroom lighting switches off |
| Multiroom Control | "I'm leaving home. Turn off all the lights" | Exposed bedroom and living room lights switch off |

These demonstrations were tested in the Home Assistant environment and captured in screen recordings.

## Technology Stack

| Technology | Application |
|---|---|
| Home Assistant OS | Smart home automation platform |
| Oracle VirtualBox | Virtualized Home Assistant environment |
| Ollama | Local AI model hosting and HTTP API |
| Qwen3 4B Instruct | Natural-language interpretation |
| YAML | Lighting, scene, and automation configuration |
| Jinja2 | Virtual lighting template logic |
| Home Assistant Assist | Conversational interaction |

## Implementation Details

### Virtual Lighting Control

A template-based virtual light represents a dimmable lighting channel.

An input-number helper stores the dimming level, and template logic maps the brightness values used by Home Assistant to a percentage-based representation.

### Scene Automation

Predefined Home Assistant scenes provide lighting presets, including:

- Movie Mode: 10% brightness
- Relax Mode: 40% brightness

### Bedtime Automation

A virtual Sleep Mode switch triggers a Home Assistant automation that turns off the bedroom lighting.

### Local AI Integration

Ollama hosts the Qwen3 model locally and exposes an HTTP API.

Home Assistant uses an Ollama conversation agent through its Assist pipeline to interpret requests and interact with exposed lighting entities, scenes, and automation controls.

The AI operates locally without requiring a cloud-hosted language model for inference.

## Repository Contents

```text
sanctuary-ai-smart-lighting/
├── README.md
├── home-assistant/
│   ├── living-room-dimmer.yaml
│   ├── living-room-template-light.yaml
│   └── living-room-scenes.yaml
└── ollama/
    └── ai-integration.md
```

The YAML files document selected configuration components used in the prototype. They are reference examples rather than a complete, independently tested installation package.

## Project Demonstration

**Video:** Coming soon.

The demonstration video covers AI dimming, scene activation, bedtime automation, and multiroom lighting control.

## Current Limitations

This prototype uses simulated lighting devices.

No physical lighting controllers, environmental sensors, or HVAC equipment are connected.

Natural-language interpretation depends on the local language model and may require explicit commands for reliable scene selection.

## Future Development

Potential extensions include:

- Integration with physical Philips Dynalite lighting controllers
- Indoor air-quality and occupancy monitoring
- HVAC and curtain automation
- Energy monitoring and reporting
- More advanced context-aware automation
- Evaluation of wellness-oriented lighting and environmental control strategies

## About the Developer

**Jojo Jose**  
**Manager – Controls & Automation**

Over eight years of professional experience in lighting control, building automation, and system integration.

Technical experience includes Philips Dynalite, KNX, DALI, BACnet, Zigbee, Z-wave, Matter,IoT lighting automation, and building management system integration.

This project represents an exploration of how practical building automation experience can be combined with locally hosted AI to develop more intuitive smart home systems.
