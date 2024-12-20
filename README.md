# TOPSIS Implementation for Pretrained Models

This repository provides a Python-based implementation of the Technique for Order of Preference by Similarity to Ideal Solution (TOPSIS). It is tailored for multi-criteria decision-making and is specifically designed to evaluate pretrained models using various performance metrics.
TOPSIS is a robust decision-making method that ranks alternatives based on their similarity to an ideal solution. This implementation focuses on ranking pretrained models using a set of defined metrics such as accuracy, precision, recall, and others.

## Installation
To set up the environment for running the TOPSIS script, ensure you have Python 3.x installed. Then, install the required dependencies using the following command:

```bash
pip install pandas numpy
```

## Usage
The script can be executed from the command line with the following syntax:

```bash
python main.py <input_file> <weights> <impacts> <output_file>
```

### Parameters:
- `<input_file>`: Path to the CSV file containing data for pretrained models.
- `<weights>`: Comma-separated weights assigned to each metric (7 metrics in total).
- `<impacts>`: Comma-separated signs for each metric (`+` for maximization, `-` for minimization).
- `<output_file>`: Path to save the output CSV file with rankings.

## Input Format
The input CSV file must contain the following columns:

1. **Text**: Descriptive information about each alternative.
2. **Models**: Names of the pretrained models being evaluated.
3. **Metrics**: Numeric values for the following metrics:
   - Accuracy
   - Precision
   - Recall
   - F1 Score
   - BLEU Score
   - ROUGE Score
   - Perplexity

```

## Output Format
The output CSV file will contain the following columns:

1. **Text**: Descriptive information about each alternative.
2. **Models**: Names of the pretrained models being evaluated.
3. **Metrics**: Original metrics from the input file.
4. **Performance_Score**: The calculated score using the TOPSIS method.
5. **Rank**: Rank assigned to each alternative based on the performance score.

```

## Example
### Command:
```bash
python main.py text_conversational.csv "0.3,0.2,0.2,0.1,0.1,0.05,0.05" "+,+,+,+,+,+,-" result.csv
```

### Output:
After running the above command, the file `result.csv` will include calculated performance scores and rankings for the pretrained models based on the provided weights and impacts.

## License
This project is open-source and distributed under the MIT License. Feel free to use, modify, and distribute it as needed.

