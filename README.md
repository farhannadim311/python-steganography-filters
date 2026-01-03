
## Project Overview

This problem set focuses on two main applications of image processing:

### 1. Colorblindness Simulation
Simulates how individuals with **Protanopia** (red-green color blindness) perceive images.
* **Technique:** Implements matrix multiplication on RGB pixel values to transform colors based on physiological models of cone sensitivity
* **Key Function:** `filter(pixels_list, color)` applies specific transformation matrices to simulate red, green, or blue color deficiencies

### 2. Steganography (Hidden Messages)
Implements algorithms to reveal "secret" images hidden inside other images using **Least Significant Bit (LSB)** encoding.
* **Technique:** Extracts hidden binary data from the least significant bits of pixel values.
* **Features:**
    * **Black & White Discovery:** Reveals hidden grayscale images embedded in 8-bit depth images[.
    * **Full Color Discovery:** Extracts hidden RGB images by processing the LSBs of the red, green, and blue channels independently.

## Prerequisites

This project requires **Python 3** and the **Pillow** library (a fork of PIL).

### Installation

If you haven't installed the dependencies yet, run:

```bash
pip install Pillow
```
## File Structure

* `ps5.py`: Main solution file containing the image processing logic and helper functions.
* `test_ps5_student.py`: Unit tests provided to verify the correctness of the image filters and bit extraction.
* `mit6_100l_f22_ps5.pdf`: Original problem set instructions.
* **Images**: Contains source images (e.g., `image_15.png`) and hidden message files (`hidden1.bmp`, `hidden2.bmp`) used for testing.

## Usage

### Running the Code
You can import the functions in a Python shell or run the script directly to process images.

```python
from ps5 import *

# Example: Simulate Protanopia (Red-Blindness)
pixels = img_to_pix('image_15.png')
transformed_pixels = filter(pixels, 'red')
pix_to_img(transformed_pixels, (width, height), 'RGB').save('output_protanopia.png')

# Example: Reveal a hidden image
secret_image = reveal_color_image('hidden2.bmp')
secret_image.show()
```
