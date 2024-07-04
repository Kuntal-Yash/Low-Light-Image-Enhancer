# Low-Light-Image-Enhancer
This project enhances low-light image quality and object detection using YOLO and Zero-DCE. It optimizes light-enhancement with DCE-Net for RGB channels, customizes loss functions, and integrates attention mechanisms. 

## MODEL:

The Zero-DCE Framework:
The DCE-Net aims to derive optimal light-enhancement curves (LE-curves) for a given input image.
These curves are applied iteratively to transform all pixels within the input's RGB channels, resulting in the final enhanced image.
Understanding Light-Enhancement Curves:
Light-enhancement curves automatically enhance low-light images, with parameters adapting based on the input image.
Three primary considerations:
Preservation of Pixel Value Range: Ensures pixel values fall within [0,1] to prevent information loss.
Monotonicity: Maintains contrast between adjacent pixels.
Curve Simplicity and Differentiability: Shapes kept simple while remaining differentiable for training.
Application of Light-Enhancement Curves:
Curves are applied independently to each RGB channel, not solely to the illumination channel.
This approach preserves original colors and reduces the risk of over-saturation.


## DCE-Net Overview:
The DCE-Net is a lightweight deep neural network designed to learn the mapping between a low-light input image and its corresponding curve parameter maps.
It operates by taking a low-light image as input and generating a set of pixel-wise curve parameter maps for higher-order curves as output.
Architecture Details:
Input: Low-light image.
Output: Set of pixel-wise curve parameter maps.
Structure: Plain CNN with seven convolutional layers featuring symmetrical concatenation.
Convolutional Layers:
Each layer comprises 32 convolutional kernels of size 3×3 and a stride of 1.
ReLU activation function is applied after each convolutional operation to introduce non-linearity.
Final Layer and Activation:
The last convolutional layer is followed by the Tanh activation function.
This layer produces 24 parameter maps for 8 iterations, with each iteration requiring three curve parameter maps for the three RGB channels.


## IMPROVEMENT ON EXISTING MODEL:
Enhancements Made to the Zero-DCE Model:
Incorporation of Additional Loss Functions:
Introduced supplementary loss functions to augment the model's training process.
These additional loss functions contribute to a more comprehensive optimization strategy.
Refinement of the Training Process:
Refined the training process by fine-tuning parameters and strategies.
Implemented optimizations to enhance the model's learning capacity and generalization ability.
Improvements Achieved:
Enhanced Low-Light Image Enhancement Performance:
By integrating additional loss functions, the model's capability to enhance low-light images is bolstered.
The refined training process results in improved performance metrics, such as image quality, brightness, and contrast.
Optimization of Loss Functions and Training Parameters:
Optimized loss functions to better align with the objectives of low-light image enhancement.
Adjusted training parameters to achieve a more effective and efficient learning process, leading to enhanced model performance.

## DATASET:Dataset Used: LoL Dataset
Training, Validation, and Testing:
The dataset used for training and validation consists of low-light images sourced from the LoL-Dataset.
It is divided into training, validation, and test sets, containing 400, 85, and 15 images, respectively.
This division enables systematic evaluation and validation of the model's performance across distinct datasets.
Content of the Dataset:
The LoL Dataset comprises low-light images intended for various computational vision tasks.
Each image within the dataset is accompanied by its corresponding ground truth enhanced version.
Purpose of Ground Truth Enhanced Versions:
Ground truth enhanced versions serve as reference standards during training and evaluation.
They provide a benchmark for assessing the effectiveness and accuracy of the model's enhancements.
 
## COMPUTATION TIME:

Total Computation Time:

The total computation time for the provided code snippet was measured from the initiation of the script to its completion.
The computation involved various tasks, including installation of required packages, dataset downloading and extraction, model building, training, and evaluation.
Time-consuming tasks such as model training and evaluation, dataset loading, and image processing contribute significantly to the overall computation time.
The total computation time is calculated as the difference between the start time and end time, utilizing the time.time() function to capture precise timestamps.
In this specific implementation, the total computation time was determined to be approximately 18 minutes