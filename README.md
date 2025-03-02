# Enhanced Image Style Transfer

## Overview
This project implements an enhanced image style transfer technique using a deep learning approach based on the VGG19 model. The goal is to blend the artistic style of one image with the content of another while preserving their key characteristics.

## Features
- Uses **VGG19** as the feature extractor for content and style representation.
- Computes **Gram matrices** to preserve the style features.
- Optimizes the generated image using **Adam optimizer**.
- Supports **custom content and style images**.
- Allows tuning of **content and style weights** for better control over the output.

## Requirements
Ensure you have the following dependencies installed before running the project:

```bash
pip install torch torchvision pillow matplotlib
```

## Usage
### 1. Load and Process Images
The images are loaded and preprocessed to match the input requirements of VGG19:
```python
content_img = load_image("path_to_content_image.jpg")
style_img = load_image("path_to_style_image.jpg")
```

### 2. Display Images
To visualize the images:
```python
imshow(content_img, "Content Image")
imshow(style_img, "Style Image")
```

### 3. Perform Style Transfer
```python
generated_img = style_transfer(content_img, style_img)
imshow(generated_img, "Generated Image")
```

## Model Explanation
- **VGG19 Feature Extraction**: Extracts feature maps from multiple layers to capture both content and style representations.
- **Content Loss**: Measures how different the generated image is from the content image.
- **Style Loss (Gram Matrix)**: Ensures the texture and patterns from the style image are transferred to the generated image.
- **Optimization**: The generated image is iteratively updated using the Adam optimizer to minimize total loss.

## Results
After running the style transfer process, the output will be an image that maintains the content of the original image while adapting the artistic style of the given style image.

## Customization
- **Adjust `style_weight` and `content_weight`** to control the balance between style and content.
- **Modify `num_steps`** to determine the number of iterations for optimization.

## Example Output
![Example Style Transfer](example_output.png)

## Acknowledgments
This project is based on the neural style transfer technique introduced by Gatys et al. (2016). The implementation uses PyTorch and the pre-trained VGG19 model.

## License
This project is open-source and available for use under the MIT License.


