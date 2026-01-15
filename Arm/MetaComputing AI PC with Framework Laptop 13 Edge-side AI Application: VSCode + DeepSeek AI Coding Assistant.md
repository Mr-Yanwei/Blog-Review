# MetaComputing AI PC with Framework Laptop 13 Edge-side AI Application: VSCode + DeepSeek AI Coding Assistant
With the rapid advancement of AI technology, traditional code editors are undergoing a quiet yet profound transformation. Visual Studio Code, as one of the world's most popular open-source code editors, has become a core enabler of this revolution, leveraging its powerful extension ecosystem and lightweight architecture. In this demonstration, we will showcase a VSCode-based AI coding assistant on emerging Arm devices (MC AI PC). It is crucial to emphasize that the implementation of AI-generated code is not merely an efficiency tool but a fundamental restructuring of development paradigms. It liberates productivity, breaks cognitive barriers, and ushers programming into a new era of intelligence, low barriers to entry, and heightened creativity.
Basic Information
- System Environment: Debian 12.11 aarch64 | Linux 6.6.89
- Hardware Platform: Framework Laptop 13 + CP8180 Arm-v9 motherboard + Mali-G720 GPU
- Details: https://metacomputing.io/collections/frontpage/products/metacomputing-aipc
Running VSCode on this platform and loading mainstream AI programming plugins reveals a groundbreaking possibility: achieving low-latency, high-privacy, and sustainably evolving local AI-assisted programming without relying on cloud APIs.

## AI Coding Assistant
- Experiment 1: Directly prompt the AI assistant to generate target code.
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/9385a01d-b265-40b9-a3aa-773b27630120" />

- Experiment 2: Inspect and correct target code. The original deduplicate_and_sort function lacked a return statement. After querying the AI assistant, the function was fixed to return the sorted array.
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/a23594c4-5f35-434f-b9a5-aa62405815a1" />

<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/849c8548-ab0a-4218-9366-28f46eeb5c48" />

## Setup Process
1. Download and install Ollama and VSCode packages:
```
# Install Ollama 
curl -fsSL https://ollama.com/install.sh | sh

# vscode download arm64 deb
https://code.visualstudio.com/Download#
```
2. Launch VSCode and install the Continue extension.
<img width="854" height="776" alt="image" src="https://github.com/user-attachments/assets/26a02918-c319-44f3-b49f-a659761c2483" />


3. Configure the Continue extension: Manually add a model provider, or edit the config file directly (reference images below).
<img width="912" height="948" alt="image" src="https://github.com/user-attachments/assets/da514189-7e66-48b1-87a4-cdbebea9849e" />

<img width="1280" height="518" alt="image" src="https://github.com/user-attachments/assets/00fd1538-bfd9-4a85-b686-b025ca3b0698" />

4. Setup complete. Begin using the coding assistant.
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/c26c7e3c-50d2-4c92-a794-f022440b7885" />


## Experimental Significance: Toward a Decentralized Intelligent Development Era
The significance of this experiment extends far beyond "getting a plugin to work." It reveals a trend: future software development will increasingly embrace Edge Intelligence.
Imagine this scenario:
- A developer writes code offline on a lightweight Arm laptop during a flight.
- Without access to documentation, the AI assistant generates equivalent implementations based on historical project context.
- All interactions occur locally, eliminating data leakage risks.
- By day, code is written; by night, the local model self-reflects, generating knowledge graphs.
- Upon waking up, the AI presents module refactoring suggestions.
This isn’t science fiction—it is an emerging reality.


## Conclusion
Stay tuned for further updates. If you too are exploring the boundaries of local AI development, we invite you to join the journey.
