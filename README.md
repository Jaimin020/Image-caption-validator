# Image Caption Validator

This repository contains a deep learning model designed to validate image captions. The model leverages pre-trained embeddings and image features to predict the compatibility of a given caption with an image. The implementation is primarily in Jupyter Notebook.

## Features

- **Deep Learning Architecture**  
  Combines image features extracted using VGG16 with caption embeddings for validation.
  
- **Pre-trained Embeddings**  
  Utilizes GloVe embeddings for text processing.

- **Custom Training**  
  Model fine-tuned using binary cross-entropy loss and SGD optimizer.

- **Demo Included**  
  Test custom image-caption pairs with the pre-trained model.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Jaimin020/Image-caption-validator.git
   cd Image-caption-validator
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the pre-trained GloVe embeddings and place them in the `data` directory:
   - [GloVe Embeddings](https://nlp.stanford.edu/projects/glove/)

4. Ensure that the necessary datasets (images and captions) are placed in the appropriate directories (`data` folder).

## Usage

### Training

1. Modify the paths in the `Image_CaptionV5.ipynb` notebook to match your directory structure.
2. Run the notebook to train the model on your dataset.

### Testing

You can validate the compatibility of a caption with an image using the pre-trained model:
```python
from test import test
image_path = "<path-to-image>"
caption = "<your-caption>"
result = test(image_path, caption)
print("Validation Result:", result)
```

### Demo
The repository also contains examples to visualize the model's predictions on sample images and captions.

## Model Architecture

The model processes:
- **Image Features**: Extracted using VGG16 (pre-trained on ImageNet).
- **Caption Embeddings**: Processed using GloVe embeddings.

The features are passed through an LSTM and fully connected layers to produce a compatibility score.

![Model Architecture](example_model_architecture.png)

## Dataset
The model expects:
- **Images**: Located in the `data/Images/train2014/` directory.
- **Captions**: Processed pickle files containing image-caption pairs.

## Results
- Achieved accuracy of 86% after 5 epochs of training.
- Loss reduced to 0.31 on the training set.

## Contributing

Contributions are welcome! Feel free to fork the repository and submit a pull request with your updates.

## Future Work

- Enhance the model by exploring transformer-based architectures.
- Add a web-based interface for easier validation.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Let me know if you'd like to make any modifications or add sections!
