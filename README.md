# Augmenter: Advanced Image Augmentation Library

**Augmenter** is a Python library designed to simplify **image augmentation** for machine learning and deep learning projects. It provides an easy-to-use interface to apply a variety of augmentation techniques and supports **randomized augmentation mixing** to generate diverse variations of each image.

---

## Features

- **Augment Entire Datasets**: Process all images in a directory, including nested subdirectories, while preserving the folder structure.
- **Extensive Augmentation Techniques**: Includes operations like flipping, rotation, blurring, brightness/contrast adjustment, grayscale conversion, noise addition, sharpening, and cropping.
- **Random Augmentation Mixing**: Combine random augmentations to create diverse variations of the same image.
- **Customizable Variations**: Control the number of augmented variations per image when using mixing.
- **Structured Output**: The augmented images are saved in the same directory structure as the original dataset.

---

## Installation

Install **Augmenter** directly from PyPI:

```bash
pip install augmenter
```

---

## Usage-1

### Basic Augmentation
To apply augmentations to all images in a folder, preserving the directory structure, use the following code:

```python
from augment_labeler import Augmenter

augmenter = Augmenter()

# Applying augmentations with mixing enabled and 3 variations per image
augmented_count = augmenter.apply(
    image_dir="./dataset",  # Path to the dataset
    augmentations=[
        "flip", 
        "rotate", 
        "blur", 
        "brightness_contrast", 
        "grayscale", 
        "noise", 
        "sharpen", 
        "crop"
    ],  # List of augmentations to apply
    save_path="./augmented_dataset",  # Path to save augmented images
    mixing=True,  # Enable mixed augmentations
    variations_per_image=3  # Create 3 variations for each image
)

print(f"Total augmented images created: {augmented_count}")
```

### Output Structure

After running the above script, the output will be saved in the `augmented_dataset` folder, preserving the original folder structure with the added augmentation variations. The directory structure will look like this:

```
augmented_dataset/
├── class1/
│   ├── img1_mix_1.jpg
│   ├── img1_mix_2.jpg
│   ├── img1_mix_3.jpg
│   ├── img2_mix_1.jpg
│   ├── img2_mix_2.jpg
│   ├── img2_mix_3.jpg
├── class2/
│   ├── img3_mix_1.jpg
│   ├── img3_mix_2.jpg
│   ├── img3_mix_3.jpg
│   ├── img4_mix_1.jpg
│   ├── img4_mix_2.jpg
│   ├── img4_mix_3.jpg
```

- Each image is augmented and saved with a `_mix_X` suffix (where `X` is the variation number).
- The folder structure is preserved for each class (e.g., `class1/`, `class2/`), making it easy to use the augmented dataset for machine learning.

---
## Usage-2

### Basic Augmentation
To apply augmentations to all images in a folder, preserving the directory structure, use the following code:

```python
from augment_labeler import Augmenter

augmenter = Augmenter()
augmented_count = augmenter.apply(
    image_dir="./dataset", 
    augmentations=["flip", "rotate", "blur"], 
    save_path="./augmented_dataset"
)

print(f"Total augmented images created: {augmented_count}")
```

### Output Structure

After running the above script, the output will be saved in the `augmented_dataset` folder, preserving the original folder structure with the added augmentation variations. The directory structure will look like this:

```
/your_project/
├── dataset/
│   ├── class1/
│   │   ├── img1.jpg
│   │   ├── img2.jpg
│   ├── class2/
│   │   ├── img3.jpg
│   ├── img4.jpg
├── augmented_dataset/
│   ├── class1/
│   │   ├── img1_flip.jpg
│   │   ├── img1_rotate.jpg
│   │   ├── img1_blur.jpg
│   │   ├── img2_flip.jpg
│   │   ├── img2_rotate.jpg
│   │   ├── img2_blur.jpg
│   ├── class2/
│   │   ├── img3_flip.jpg
│   │   ├── img3_rotate.jpg
│   │   ├── img3_blur.jpg
│   ├── img4_flip.jpg
│   ├── img4_rotate.jpg
│   ├── img4_blur.jpg
```
- The folder structure is preserved for each class (e.g., `class1/`, `class2/`), making it easy to use the augmented dataset for machine learning.

---

## Supported Augmentations

- **flip**: Horizontal flip
- **rotate**: Random rotation (up to ±45 degrees)
- **blur**: Gaussian blur
- **brightness_contrast**: Random brightness and contrast adjustments
- **grayscale**: Convert image to grayscale
- **noise**: Add Gaussian noise
- **sharpen**: Sharpen the image
- **crop**: Random resized cropping

---
---

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes and push them to your fork.
4. Open a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/IMApurbo/augmenter/LICENSE) file for details.

---

## Release Notes

### v0.1.0
- Initial release.
- Support for multiple augmentations and structured dataset output.
- Added random augmentation mixing and customizable variations.

---

## Author

Developed by **[AKM Korishee Apurbo](https://github.com/IMApurbo)**. Feel free to reach out with questions, suggestions, or contributions!
