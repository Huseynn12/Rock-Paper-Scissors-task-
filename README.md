# Rock-Paper-Scissors-task-
markdown
# Task [X]: Rock-papper-scissor

**Student:** Huseyn  
**ID:** S306  
**Seed:** 2024306

## Presentation
[View Presentation Slides](https://1drv.ms/p/c/e9de17b25a7f2ce3/IQCr6KuLjFwzRJeTOFIRbXtuAcZsxozwkBjMgjimA-A116I)

## Dataset
- **Name:** Kaggle Rock-Paper-Scissors  
- **Classes:** 3 (rock, paper, scissors)  
- **Training samples:** 200304130
- **Test samples:** 29453177

## Model Architecture
- **Type:** CNN
- **Convolutional layers:** [Number]
- **Fully connected layers:** [Number]
- **Total parameters:** [Number]

## Training Comparison

### Version 1
- **Learning rate:** 0.001
- **Batch size:** 32
- **Optimizer:** adam
- **Test accuracy:** 99.33

### Version 2
- **Learning rate:** 0.0001
- **Batch size:** 64
- **Optimizer:** adam
- **Test accuracy:** 95.96%

### Best Result
- **Best version:** Version 1
- **Final test accuracy:** 99%
- **Target accuracy:** >=99%
- **Status:** ✓ Achieved 

## Analysis
- **Best performing class:** papper rock
- **Worst performing class:** scissors
- **Key observations:** [2-3 sentences about what you learned]

## Files
- `notebook.ipynb`: [Uploading rock-paper-scissors-task (1) (1).ipynb…]()

IPYNB
- `results/training_comparison.png`: Comparison of Version 1 vs Version 2
- `results/confusion_matrix.png`: Confusion matrix from best model
- `results/predictions.png`: Sample predictions
The code uses a Convolutional Neural Network (CNN). Here is how each part works:
1. Data PreprocessingBefore training, we prepare the images:Resize: All images are resized to $128 \times 128$ pixels so the model gets a standard input.Normalization: We change pixel values to a range of $[-1, 1]$ using transforms.Normalize. This helps the model learn faster
2. The CNN Layers (Feature Extraction)Our model looks at the images using three "Blocks":Convolutional Layers (Conv2D): These layers act like filters. They find edges, shapes, and textures of the hand (Rock, Paper, or Scissors).ReLU Activation: This function removes negative values and helps the model understand complex patterns.MaxPool2D: This reduces the size of the image data. It keeps the most important information and makes the code run faster.
3. The Classifier (Decision Making)After the CNN blocks, we have the Classifier part:Flatten: It converts the 2D image features into a 1D list (vector).Linear Layer: This is a fully connected layer that connects features to the classes.Dropout (0.5): This is a very important tool. It randomly "turns off" 50% of neurons during training. This prevents Overfitting (meaning the model won't just memorize the pictures, it will actually learn to recognize hands).Softmax (Output): The final layer gives us a probability for each class (Rock, Paper, or Scissors).
4. Training ProcessWe compare two versions of the model:Optimizer (Adam): This is the "brain" that updates the model weights to reduce errors.Loss Function (CrossEntropyLoss): This measures how "wrong" the model's predictions are.Versions: * Version 1 ($LR = 0.001$): High speed, fast results.Version 2 ($LR = 0.0001$): Slow speed, but more careful learning.
