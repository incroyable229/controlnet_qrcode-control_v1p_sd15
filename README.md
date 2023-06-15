---
tags:
- stable-diffusion
- controlnet
license: openrail++
language:
- en
---
# QR Code Conditioned ControlNet Models for Stable Diffusion 1.5

![1](https://www.dropbox.com/s/fxyuqpot2z2ftty/5.png?raw=1)

## Model Description

This repo holds the safetensors & diffusers versions of the QR code conditioned ControlNet for Stable Diffusion v1.5.
The Stable Diffusion 2.1 version is marginally more effective, as it was developed to address my specific needs. However, this 1.5 version model was also trained on the same dataset for those who are using the older version.

## Performance and Limitations

These models perform quite well in most cases, but please note that they are not 100% accurate. In some instances, the QR code shape might not come through as expected. You can increase the ControlNet weight to emphasize the QR code shape. However, be cautious as this might negatively impact the style of your output.**To optimize for scanning, please generate your QR codes with correction mode 'H' (30%).**

To balance between style and shape, a gentle fine-tuning of the control weight might be required based on the individual input and the desired output, aswell as the correct prompt. Some prompts do not work until you increase the weight by a lot. The process of finding the right balance between these factors is part art and part science. For the best results, it is recommended to generate your artwork at a resolution of 768. This allows for a higher level of detail in the final product, enhancing the quality and effectiveness of the QR code-based artwork.

## Installation

The simplest way to use this is to place the .safetensors model and its .yaml config file in the folder where your other controlnet models are installed, which varies per application. 
For usage in auto1111 they can be placed in the webui/models/ControlNet folder. They can be loaded using the controlnet webui extension which you can install through the extensions tab in the webui (https://github.com/Mikubill/sd-webui-controlnet). Make sure to enable your controlnet unit and set your input image as the QR code. Set the model to either the SD2.1 or 1.5 version depending on your base stable diffusion model, or it will error. No pre-processor is needed, though you can use the invert pre-processor for a different variation of results. 768 is the preferred resolution for generation since it allows for more detail.
Make sure to look up additional info on how to use controlnet if you get stuck, once you have the webui up and running its really easy to install the controlnet extension aswell.