

# FaceSwap Extension - Automatic 1111 - Proof of Concept



The main objective of this extension is to enable face swapping for single images in stable diffusion.

To ensure compatibility, this extension currently runs only on CPU. However, it can be easily ported to GPU for improved performance.

![example](example/example.png)

**This extension is not intended to allow the generation of nsfw content or deepfake content. Any modification of the code to enable the generation of such content is prohibited. Any explanation on this repository of how to disable protection will be removed.**

The code will follow European regulations in place for this type of software. In particular, visible or invisible watermarks may be integrated if required by law. You must not use this extension if your country's legislation prohibits it.



## Install

To install the extension, follow these steps:

+ Clone the repository to your automatic 1111 extensions directory.
+ Download the pre-trained model used by "Roop" and place it in the models directory of this extension (/stable-diffusion-webui/extensions/sd-webui-faceswap/models/ or /stable-diffusion-webui/models/FaceSwap). The model file required is "inswapper_128.onnx".Mirrors are given the roop project [installation guide](https://github.com/s0md3v/roop/wiki/1.-Installation).

On Windows, Microsoft Visual C++ 14.0 or greater is required. [During the install, make sure to include the Python and C++ packages.](https://github.com/s0md3v/roop/issues/153)

The inswapper_128.onnx model I use has the following sha1sum : 17a64851eaefd55ea597ee41e5c18409754244c5

**Use of the models must comply with their respective terms of the license (see [insightface repository](https://github.com/deepinsight/insightface/tree/master/python-package))**. No model will be directly provided or hosted here.

## Usage

To use the FaceSwap extension, follow these instructions:

1. In the face swap box, import an image containing a face.
2. Click on the "Activate" before generate.
3. Optionally, select the face number you wish to swap (from right to left) if multiple faces are detected in the image.
4. The resulting swapped face will be displayed.
5. If the quality is not satisfactory (and it is often quite average), you can try using the "Restore Face" feature or explore additional options in the "Extra" tab for further improvement. You can also select an upscaler from the menu. This will activate CodeFormer and the chosen upscaler (scale=1). The result may be satisfactory, but gives less control than the extra tab.

### Img2Img :

You can choose to activate the swap on the source image or on the generated image, or on both. Activate on source image allows you to start from a given base and apply the diffusion process to it.

Inpainting should work but only the masked part will be swapped.


## Credits

+ The developers of roop for their great work.
+ deepinsight for their insightface project, which offers a well-crafted library and models that have greatly enhanced the capabilities of this project.
