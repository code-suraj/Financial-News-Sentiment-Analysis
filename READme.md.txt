# Financial News Sentiment Analysis

This project aims to develop a sentiment analysis model for financial news headlines using the GPT-3.5-turbo model. The project involves zero-shot and few-shot prompting, data preparation, fine-tuning the model, and testing its performance in both controlled and real-world scenarios.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Zero-Shot Prompting](#zero-shot-prompting)
3. [Few-Shot Prompting](#few-shot-prompting)
4. [Data Preparation](#data-preparation)
5. [Fine-Tuning](#fine-tuning)
6. [Results](#results)
7. [Real-World Testing](#real-world-testing)
8. [Conclusion](#conclusion)
9. [Files in the Repository](#files-in-the-repository)
10. [How to Run the Project](#how-to-run-the-project)
11. [Acknowledgements](#acknowledgements)

## Project Overview

The objective of this project is to fine-tune a GPT-3.5-turbo model to accurately classify sentiments of financial news headlines into three categories: positive, neutral, and negative. The model's performance was evaluated in zero-shot and few-shot prompting scenarios, followed by a fine-tuning phase to enhance accuracy.

## Zero-Shot Prompting

In the zero-shot prompting phase, 60 news items were used to determine the baseline accuracy without providing any prior examples to the model.

- **Zero-Shot Accuracy:** 91.67%

## Few-Shot Prompting

In the few-shot prompting phase, the model was given 4 examples each of positive, negative, and neutral sentiments before making predictions on 60 news items.

- **Few-Shot (12) Accuracy:** 93.33%

## Data Preparation

The data preparation involved:
- Loading financial news headlines from `Sentences_AllAgree.txt` and `Sentences_75Agree.txt`.
- Combining the datasets and encoding the sentiments as 'positive', 'neutral', and 'negative'.
- Selecting 150 samples of each sentiment for fine-tuning, creating a balanced dataset of 450 samples saved to `fine_tuning_data.csv`.
- Excluding these samples from the original dataset and selecting 500 new, non-overlapping news items for testing, saved to `fine_tuning_test.csv`.

## Fine-Tuning

The fine-tuning process involved:
- Creating a JSONL file with structured prompts and completions for the chat model.
- Uploading the file to OpenAI's platform and initiating the fine-tuning job with the ID `ftjob-DyFPG9XxLzCTG4XwPmJ5YAme`.
- Testing the fine-tuned model on 500 new, randomly selected news items.

- **Fine-Tuned Model Accuracy:** 94.00%

The confusion matrix for the fine-tuned model showed high accuracy, particularly in classifying neutral sentiments accurately.

## Results

The results from different phases are as follows:
- **Zero-Shot Accuracy:** 91.67%
- **Few-Shot (12) Accuracy:** 93.33%
- **Fine-Tuned Model Accuracy:** 94.00%

## Real-World Testing

The fine-tuned model was tested on a set of real-world financial news headlines. The results were compared with manually assigned sentiments.

- **Manual Accuracy Check:**
  - **Correct Predictions:** 11
  - **Total Predictions:** 11
  - **Accuracy:** 100%

## Conclusion

The fine-tuned model performed exceptionally well, achieving high accuracy rates in both controlled and real-world testing scenarios. The results demonstrate the model's capability to accurately classify the sentiment of financial news headlines.

### Key Findings:
- **Zero-Shot Accuracy:** 91.67%
- **Few-Shot (12) Accuracy:** 93.33%
- **Fine-Tuned Model Accuracy:** 94.00%
- **Real-World Testing Accuracy:** 100%

## Files in the Repository

- `Homework-4.pdf`: Detailed report of the project.
- `Homework_4.ipynb`: Jupyter Notebook with the code implementation.

## How to Run the Project

1. **Clone the repository:**
   ```sh
   git clone https://github.com/yourusername/financial-news-sentiment-analysis.git
   cd financial-news-sentiment-analysis
