# Scaling Laws in Symbolic Music Modeling

This repository contains the code for a course project studying scaling laws in
symbolic music generation. The project compares decoder-only Transformer models
with RNN (LSTM) baselines using symbolic music represented in ABC notation.

The objective is to analyze how validation loss scales with increasing model
size and to compare architectural efficiency, training cost, and sample quality
between Transformers and RNNs.

---

## Files in This Repository

All files are provided directly in the repository root for simplicity.

- **tokenization.ipynb**  
  Performs full data preprocessing and tokenization, including:
  - MIDI to ABC conversion  
  - Cleaning and filtering of ABC files  
  - Chunking long sequences  
  - Note-level vocabulary construction  
  - Train/validation/test split generation  

- **transformer.ipynb**  
  Trains a family of decoder-only Transformer language models of varying sizes
  (Tiny to XL) using a nanoGPT-style implementation. Models are trained for
  exactly one epoch to study scaling behavior.

- **rnn.ipynb**  
  Trains LSTM-based RNN baseline models matched in parameter count to the
  Transformer models. Uses the same dataset, tokenization, and training setup
  for fair comparison.

- **best_model.ipynb**  
  Trains the best-performing Transformer model using a fixed time budget.
  Includes checkpointing, validation-based model selection, final test
  evaluation, perplexity computation, and qualitative music sample generation
  (ABC and MIDI).

- **comparison.ipynb**  
  Compares Transformer and RNN models by:
  - Validation loss vs. model size  
  - Power-law scaling fits  
  - Training time efficiency  
  - Memory efficiency  
  - Sample efficiency analysis  

---
## Data and Files

The notebooks use absolute file paths (local machine and Google Colab) that were
used during the original experiments.

Due to the large size of the dataset, the following files are not included in
this repository:

- Raw MIDI files
- Preprocessed ABC files
- Tokenized text files
- Binary `.bin` files
- Model checkpoints
- Generated MIDI files

To reproduce the experiments, download the Lakh MIDI Dataset, update the paths
in `tokenization.ipynb`, and run the preprocessing and training notebooks.

---

## Notes

- Model configurations are defined inside the notebooks
- Large files are excluded due to GitHub size limits
- This repository is for academic coursework and reproducibility

