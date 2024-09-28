
# Get Sequences from Proteinortho

This Python script extracts nucleotide and protein sequences from `.pep` and `.cds` files based on a Proteinortho `.tsv` table. The script allows the user to set the maximum proportion of missing species and low copy numbers to filter orthologous groups. The output consists of FASTA files for each orthologous group that meet the user-specified criteria.

## Features

- Extracts nucleotide and protein sequences for orthologous groups from Proteinortho `.tsv` files.
- Allows filtering by species missing proportion and low copy numbers.
- Outputs separate FASTA files for each orthologous group.

## Requirements

- Python 3.x
- [Biopython](https://biopython.org/) (`pip install biopython`)
- [pandas](https://pandas.pydata.org/) (`pip install pandas`)
- Numpy (`pip install numpy`)

## Installation

1. Clone the repository:

    \`\`\`bash
    git clone https://github.com/yourusername/get_seq_from_proteinortho.git
    \`\`\`

2. Install the required Python packages:

    \`\`\`bash
    pip install biopython pandas numpy
    \`\`\`

## Usage

Run the script with the following command:

\`\`\`bash
python get_seq_from_proteinortho.py -i <input_proteinortho.tsv> -o <output_directory> -p <max_missing_species_proportion> -c <max_copy_number>
\`\`\`

### Arguments

- \`-i\`, \`--infile\`: **Required**. The Proteinortho output file (in `.tsv` format). Default is \`myproject.proteinortho.tsv\`.
- \`-o\`, \`--output\`: **Required**. Name of the output directory where the sequence files will be saved. Default is \`output2\`.
- \`-p\`, \`--missing\`: **Required**. Maximum allowed proportion of missing species. Default is \`0.3\`.
- \`-c\`, \`--copy\`: **Required**. Maximum allowed low copy number per species. Default is \`1\`.

### Example

\`\`\`bash
python get_seq_from_proteinortho.py -i myproject.proteinortho.tsv -o output_sequences -p 0.3 -c 1
\`\`\`

In this example:
- The input file is \`myproject.proteinortho.tsv\`.
- The output folder is named \`output_sequences\`.
- A maximum of 30% missing species per orthologous group is allowed.
- A maximum of 1 copy number is allowed for each species.

## Output

The script will generate a set of FASTA files in the specified output directory. Each orthologous group will have two corresponding FASTA files:
- \`orthoX_cds.fasta\`: Contains the nucleotide sequences for the orthologous group.
- \`orthoX_pep.fasta\`: Contains the protein sequences for the orthologous group.

## Error Handling

- If the output directory already exists, the script will exit with a message indicating that the directory already exists.
- If any sequence in an orthologous group has more copies than the allowed limit, that group will not be written to the output.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## Contact

If you have any questions or suggestions, feel free to contact me at [j.he930724@gmail.com].
