# Topsis_experimental: TOPSIS Analysis Python Package

## Overview

topsis_experimental is a Python package that implements the Technique for Order Preference by Similarity to Ideal Solution (TOPSIS) for multi-criteria decision-making (MCDM). It provides a straightforward and efficient way to evaluate and rank a set of alternatives based on conflicting criteria.

## Key Features

User-friendly command-line interface for easy execution.
Supports both numerical and categorical data.
Handles equal weights and impacts, as well as positive and negative impacts.
Generates a TOPSIS score for each alternative, indicating its similarity to the ideal solution.
Provides ranking of alternatives based on their TOPSIS scores.
Installation

To install topsis_experimental using pip:

```bash
pip install topsis_experimental
```



You can use topsis_experimental from the command line as follows:

```bash
topsis_experimental input.csv weights impacts output.csv
```

where:

input.csv: The input CSV file containing the decision matrix (alternatives and criteria).
weights: Comma-separated list of weights for each criterion (numerical, equal to the number of criteria).
impacts: Comma-separated list of impacts for each criterion (+ for positive, - for negative).
output.csv: The output CSV file containing the TOPSIS scores and rankings.
Example

Assume you have a CSV file data.csv with the following structure:

| Fund Name | P1   | P2   | P3  | P4   | P5    |
|-------|------|------|-----|------|-------|
| M1    | 0.85 | 0.72 | 4.6 | 41.5 | 11.92 | 
| M2    | 0.66 | 0.44 | 6.6 | 49.4 | 14.28 | 
| M3    | 0.9  | 0.81 | 6.7 | 66.5 | 18.73 | 
| M4    | 0.8  | 0.64 | 6.9 | 69.7 | 19.51 | 
| M5    | 0.84 | 0.71 | 4.7 | 36.5 | 10.69 | 
| M6    | 0.91 | 0.83 | 3.6 | 42.3 | 11.91 | 
| M7    | 0.65 | 0.42 | 6.9 | 38.1 | 11.52 | 
| M8    | 0.71 | 0.5  | 3.5 | 60.9 | 16.4  | 
And you want to perform TOPSIS with weights 1,1,1,2,1 and all positive impacts (+++-+).

Run the following command:

```bash
python topsis_experimental.py data.csv "1,1,1,2,1" "+,+,+,-,+" results.csv
```

This will create a file results.csv with the TOPSIS scores and rankings.
| Model | P1   | P2   | P3  | P4   | P5    | Topsis score       | Rank |
|-------|------|------|-----|------|-------|--------------------|------|
| M1    | 0.85 | 0.72 | 4.6 | 41.5 | 11.92 | 0.3267076760116426 | 6    |
| M2    | 0.66 | 0.44 | 6.6 | 49.4 | 14.28 | 0.6230956090525585 | 2    |
| M3    | 0.9  | 0.81 | 6.7 | 66.5 | 18.73 | 0.5006083702087599 | 5    |
| M4    | 0.8  | 0.64 | 6.9 | 69.7 | 19.51 | 0.6275096427934269 | 1    |
| M5    | 0.84 | 0.71 | 4.7 | 36.5 | 10.69 | 0.3249142875298663 | 7    |
| M6    | 0.91 | 0.83 | 3.6 | 42.3 | 11.91 | 0.2715902624653612 | 8    |
| M7    | 0.65 | 0.42 | 6.9 | 38.1 | 11.52 | 0.5439263412940541 | 4    |
| M8    | 0.71 | 0.5  | 3.5 | 60.9 | 16.4  | 0.6166791918077927 | 3    |

Additional Notes

The weights and impacts must be separated by commas and have the same number of elements as the number of criteria.
For more advanced usage, see the source code or consider creating a custom Python script.