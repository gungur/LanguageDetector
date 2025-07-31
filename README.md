# Language Detection Program

## Overview

This program detects whether a given text is more likely to be English or Spanish based on character frequency analysis. It implements a Naive Bayes classifier using multinomial probability distributions for English and Spanish languages.

## Files

The program consists of several files:

- `hw2.py`: Main Python script containing the implementation
- `e.txt`: English character probability distribution
- `s.txt`: Spanish character probability distribution
- `letter.txt`: Input text file to analyze (you provide this)
- `letterX.txt` and `letterX_out.txt`: Example input/output files

## How It Works

1. **Character Counting (`shred` function)**:
   - Counts occurrences of each letter (A-Z) in the input file, ignoring case and non-alphabetic characters

2. **Probability Calculation**:
   - Uses pre-trained character probability distributions for English and Spanish
   - Computes log probabilities to avoid underflow

3. **Classification**:
   - Calculates F(English) and F(Spanish) scores
   - Uses these to compute the posterior probability that the text is English

## Usage

1. Prepare your input text in a file named `letter.txt`
2. Run the program: `python hw2.py`
3. The program will output four results (Q1-Q4)

### Output Explanation

- **Q1**: Shows the count of each letter in the input file
- **Q2**: Shows X₁*log(e₁) and X₁*log(s₁) for the letter 'A'
- **Q3**: Shows F(English) and F(Spanish) scores
- **Q4**: Shows the probability that the text is English

## Example Outputs

See the provided `letterX_out.txt` files for examples of different outputs:

- `letter0.txt`: Mostly English text → high probability English (0.9894)
- `letter1.txt`: Minimal text → neutral probability (0.6079)
- `letter2.txt`: English poem → clearly English (1.0000)
- `letter3.txt`: Spanish text → clearly not English (0.0000)
- `letter4.txt`: German text → interestingly classified as English (1.0000)

## Requirements

- Python 3.x
- No external dependencies beyond standard library

## Limitations

- Only works with Latin alphabet texts
- Trained specifically for English vs. Spanish discrimination
- May not work well with very short texts or texts containing mostly symbols
- As shown with German text, may misclassify other languages as English

## Future Improvements

- Add support for more languages
- Implement smoothing for unseen characters
- Add n-gram features for better accuracy
- Create a proper command-line interface
