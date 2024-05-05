# Implementation of finetining for phi 1.5

## Preparing datasets

There was used 3 datasets that was made from below data: 

1. [Kotlin github](https://github.com/JetBrains/kotlin)
2. [Python test dataset](https://huggingface.co/datasets/microsoft/codexglue_method_generation/viewer/default/test)
3. [Kotlin test dataset](https://huggingface.co/datasets/codkiller0911/kotlin_code)

The first dataset includes only '.kt' and '.kts' files from GitHub. Both last test datasets consist solely of prompt and result information, which will be saved as 'input' and 'output' respectively.

## How error calculation work

The Levenshtein distance is utilized to measure the dissimilarity between the model's output and the expected output. This distance is calculated, then divided by the sum of the lengths of both results, and added to a list. Finally, the median value is selected from this list.

## How to use 

To use this tool, you can either load and run it on your local device, requiring a minimum of 24 GB of GPU memory, or run it on Google Colab with at least an L4 GPU. Afterward, you can execute all cells in order, but the third one will prompt you to upload a user access token with write permissions from Hugging Face.

## Results

As depicted in the graph below, there are no significant changes in the quality of the code. Python code approaches an ideal answer by 0.1, while Kotlin code diverges from it. This discrepancy could be attributed to several factors: a small number of epochs, poor dataset quality, the absence of an optimizer, and bad quality check off code. In the future, all the problems mentioned above can be fixed.

![Error value from epoch caunt](https://drive.google.com/uc?export=view&id=1OXms8HwE2t7yWNdGkV-mJguGd0wYTAh1)
