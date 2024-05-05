# Implementation of finetining for phi 1.5

## Preparing datasets

There was used 3 datasets that was made from below data: 

1. [Kotlin github](https://github.com/JetBrains/kotlin)
2. [Python test dataset](https://huggingface.co/datasets/microsoft/codexglue_method_generation/viewer/default/test)
3. [Kotlin test dataset](https://huggingface.co/datasets/codkiller0911/kotlin_code)

First dataset use only '.kt' and '.kts' files from github. Both test dataset use only prompt and result information. This information will be save as 'input' and 'output'.

## How error calculation work

There used Levenshtein distance that will be calculated between model result, that was received, and what it should be. After calculation of distance, this value will be divided by sum of length of both results, and added into list. In the end there will be chosen median value.

## How to use 
