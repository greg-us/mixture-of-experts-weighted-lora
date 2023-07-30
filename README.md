# mixture-of-experts-weighted-lora
peft patch and mixture of expert implementation for transformers

## Patch for PEFT Library Multi-LoRa inference Support

PEFT doesn't inherently support simultaneous usage of multiple LoRa (Long Range) devices. While you can load multiple LoRa adapters, only one can be utilized at a time. Merging several LoRa weights is possible, but doing so will bind the model to these new weights.

The code in this repository provides a solution to patch Linear LoRa layers from PEFT (both standard and quantized). This patch offers the following capabilities:

- Utilize multiple weighted LoRa without merging them;
- Apply different weights for each sample in a batch.

Downsides :

- Activating every LoRa layer will increase the inference time;
- Currently, only the Linear layer is supported (this work is primarily focused on Linear Layers (LLM) LoRa usage).

## Mixture of experts

It's the newt step. I'm working on it.
