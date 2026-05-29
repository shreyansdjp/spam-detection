# Spam Detection

This project is a small SMS spam classification workflow built with Python, pandas, scikit-learn, and Jupyter notebooks.

## What this project does

- Loads the raw SMS dataset from `data/spam.csv`
- Preprocesses the text in `preprocessing.ipynb`
- Produces a cleaned dataset at `data/spam_preprocessed.csv`
- Uses a text classification pipeline (TF-IDF + Naive Bayes) in `main.ipynb` for spam detection

## Project structure

- `preprocessing.ipynb` — cleans and prepares the SMS text data
- `main.ipynb` — trains and evaluates the spam classifier
- `data/spam.csv` — original dataset
- `data/spam_preprocessed.csv` — cleaned dataset used for modeling
- `pyproject.toml` — project dependencies

## Dataset

The raw dataset contains SMS messages labeled as:

- `ham` = legitimate message
- `spam` = unwanted promotional or scam message

The preprocessing step:

- converts labels to numeric values (`ham = 0`, `spam = 1`)
- lowercases text
- removes phone-number-like patterns and digits
- strips punctuation and extra whitespace

## Setup

This project works well with `uv` for dependency management.

1. Install `uv` if you do not already have it:

   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

2. Create and activate the environment, then install dependencies:

   ```bash
   uv venv
   source .venv/bin/activate
   uv pip install -e .
   ```

3. Open the notebooks in Jupyter and run them in order:
   - `preprocessing.ipynb`
   - `main.ipynb`

## Usage

Run the preprocessing notebook first to generate the cleaned dataset:

```bash
python -m jupyter notebook preprocessing.ipynb
```

Then open and run `main.ipynb` to build and evaluate the model.

## Notes

This repository is intended as a simple example of text classification for spam detection. The preprocessing notebook is already set up, and the main training notebook can be extended with model evaluation, metrics, and further experimentation.
