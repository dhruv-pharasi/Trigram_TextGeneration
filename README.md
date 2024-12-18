# Trigram-Based Text Generation

## Overview

This project implements a text generation model using a trigram-based approach. The model learns the probabilities of word sequences from input text and generates realistic sentences by predicting the next word based on the current context.

## Features

- **Trigram Model**: Builds a model based on word triplets (trigrams).
- **Probability-Based Generation**: Generates text using probabilities calculated from trigram frequencies.
- **Top 4 Candidate Selection**: Randomly selects the next word from the top 4 most probable candidates to add diversity.
- **Random Start**: The model can begin generation from a random starting sequence in the training data.

## Requirements

- Python 3.7+
- Libraries:
  - `heapq` (standard library)
  - `random` (standard library)
  - `collections` (standard library)
  - `re` (standard library)
- Dataset:
  - [WikiText](https://huggingface.co/datasets/wikitext) (for training large-scale models)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/dhruv-pharasi/Trigram_TextGeneration.git
   ```
2. Ensure you have Python installed.
3. Install additional libraries if required (e.g., for preprocessing).

## Usage

### Training the Model

1. Provide a text corpus as a string.
2. Preprocess the text (clean, tokenize, etc.) and feed it into the model.
3. Build trigram and bigram frequency dictionaries:
   ```python
   trigram_counts, bigram_counts = build_trigram_counts(words)
   ```

### Generate Text

- **Live Text Generation with Random Start**:

  ```python
  starting_bigrams = list(trigram_counts.keys())
  
  start_seq = " ".join(random.choice(starting_bigrams))
  generate_text(trigram_counts, bigram_counts, start_seq, length=15)
  ```

- **Customize Starting Sequence**:

  ```python
  start_seq = "once upon"
  generate_text(trigram_counts, bigram_counts, start_seq, length=15)
  ```

## Example

### Input Corpus

```text
Once upon a time, there was a brave princess who fought dragons. The princess loved adventures.
```

### Sample Output

```text
once upon a time there was a brave princess who loved adventures and fought dragons
```

## Files

- `Trigram_TextGeneratorModel.ipynb`: Contains the implementation of the trigram-based text generation.
- `README.md`: Documentation for the project.

## Future Enhancements

- Add support for larger n-grams (e.g., 4-grams, 5-grams).
- Implement smoothing techniques (e.g., Laplace smoothing) for better handling of unseen sequences.
- Integrate with external APIs for training on large datasets.
- Provide a graphical interface for interactive text generation.

## Author

[Dhruv Pharasi](https://github.com/dhruv-pharasi)

