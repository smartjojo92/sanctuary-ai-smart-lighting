# Sanctuary AI – Smart Lighting Automation

# Local AI-Powered Smart Home Prototype

A working proof-of-concept integrating **Home Assistant**, **Ollama**, and **Qwen3 4B Instruct** to control simulated smart lighting systems using natural-language commands.

## Project Overview

This project demonstrates how a locally hosted large language model can interpret user requests and control lighting entities, dimming levels, and predefined scenes through Home Assistant.

The prototype is inspired by real-world lighting control systems, including Philips Dynalite.

## System Architecture

User Command → Home Assistant Assist → Ollama / Qwen3 → Home Assistant Actions → Virtual Lighting Devices

## Features

- Natural-language lighting control
- Virtual dimming from 0–100%
- Bedroom and living room lighting control
- Relax scene at 40% brightness
- Movie scene at 10% brightness
- AI-driven lighting scene selection
- Multiroom lighting control
- Bedtime automation using Sleep Mode

## Technology Stack

| Technology | Purpose |
|---|---|
| Home Assistant OS | Automation platform |
| Oracle VirtualBox | Virtual machine environment |
| Ollama | Local AI inference and API |
| Qwen3 4B Instruct | Natural-language interpretation |
| YAML | Automation and service configuration |
| Jinja2 | Dynamic lighting templates |
| Home Assistant Scenes | Preset-based lighting control |

## Example Commands

**Movie Mode**

"I'm going to watch a movie in the living room. Choose the appropriate lighting scene and activate it."

Result: The AI activates the Movie Mode scene and sets the virtual living room lighting to 10%.

**Multiroom Control**

"I'm leaving home. Turn off all the lights."

Result: The AI switches off the exposed bedroom and living room lights.

**Bedtime Automation**

"Buddy, I'm going to bed. Please get my bedroom ready."

Result: Sleep Mode is activated, triggering the bedroom lighting automation.

## Current Scope

This is a software-based prototype using simulated lighting entities. No physical lighting controllers or sensors are connected at this stage.

## Planned Enhancements

- Occupancy-based automation
- HVAC and curtain control
- Sensor and energy monitoring
- Physical Philips Dynalite integration through a compatible gateway
- More advanced context-aware AI automation

## Project Demonstration

Demo video: Coming soon.

## Author

Controls and Automation professional with experience in Philips Dynalite, KNX, DALI, BACnet, and building automation systems.

This project explores how locally hosted AI can enhance conventional lighting control and smart-building interfaces.
