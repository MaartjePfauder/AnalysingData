# Assignment 3 – Probing and Prompting Large Language Models

## Overview
This assignment investigates how Large Language Models (LLMs) can be analysed using probing and prompting techniques. The assignment consists of two parts. Part 1 explores whether an LLM internally represents a story closer to its book or movie version through a research proposal and a small prompt experiment. Part 2 investigates whether an LLM can classify song lyrics by genre using zero-shot and few-shot prompting strategies. The implementation for Part 2 was done in Python using Ollama, pandas, sklearn, seaborn, and matplotlib.

## Research Questions

### Part 1
Does a Large Language Model internally represent *Harry Potter and the Order of the Phoenix* closer to the book or the movie version, and does this differ across narrative information types such as plot, characters, and tone?

### Part 2
Can a Large Language Model correctly classify song lyrics into genres using zero-shot and few-shot prompting, and how does performance vary between prompting strategies and genres?

## Method

### Part 1
A research design was developed to investigate how LLMs internally represent narratives across different media. The proposed methodology includes collecting narrative facts from book and movie sources, annotating them as book-specific, movie-specific, or shared, and analysing model representations using embeddings and linear probes. In addition, a small prompt experiment with Llama (via Ollama) was conducted to test whether the model reproduces book knowledge, movie knowledge, or blended representations.

### Part 2
The LLM was prompted to classify song lyrics into genres using zero-shot and few-shot prompting. To ensure the experiment could run within reasonable time constraints, only the first 200 characters of each lyric were used. Initially three few-shot examples per genre were tested, but this resulted in runtimes exceeding six hours. Therefore this was reduced to two examples per genre.

The experiment included sampling a subset of the dataset, creating prompts, inspecting raw outputs, cleaning predictions, calculating Precision/Recall/F1, and analysing confusion matrices.

## Evaluation
Performance was evaluated using Precision, Recall and F1 score. In addition, confusion matrices were created to analyse performance differences across genres and to investigate which genres were most often confused by the model.

## Results
*(See reports for detailed results and discussion)*

Part 1 shows that the model often produces blended or incorrect narrative information. Part 2 shows that few-shot prompting slightly improves classification performance compared to zero-shot prompting, although overall performance remains limited due to model size and runtime constraints.

## Repository Structure
Assignment3/
│
├── Part1_report.pdf
├── Part2_report.pdf
├── Part2_code.ipynb
├── genreLyrics_train.csv
├── genreLyrics_test.csv
├── genre_predictions_sample.csv
├── run_settings.txt
├── confusion_matrix_zero_shot.png
├── confusion_matrix_few_shot.png
└── README.md

## Files included

- **Part1_report.pdf** → Research proposal and mini experiment  
- **Part2_report.pdf** → Results and discussion  
- **Part2_code.ipynb** → Python implementation  
- **genreLyrics_train.csv** → Training data  
- **genreLyrics_test.csv** → Test data  
- **genre_predictions_sample.csv** → Sample predictions used for inspection  
- **run_settings.txt** → Model configuration and runtime settings  
- **confusion_matrix_zero_shot.png** → Zero-shot classification confusion matrix  
- **confusion_matrix_few_shot.png** → Few-shot classification confusion matrix  

## Notes
The model used for Part 2 was **llama3.2:1b**, which was selected due to hardware limitations. Runtime optimizations such as lyric truncation and reducing the number of few-shot examples were necessary to complete the experiment. The confusion matrices and prediction samples are included to improve transparency and reproducibility of the results.

All code is documented and reproducible using the provided notebook.
