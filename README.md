# [L-GRAAL: Lagrangian GRAphlet-based Network Aligner](https://doi.org/10.1093/bioinformatics/btv130)

A novel global network alignment tool that combines an efficient solver based on Lagrangian relaxation with a scoring function based on graphlet statistics.

## Authors

- Noel Malod-Dognin
- Natasa Przulj

**Corresponding Author:** Dr. Noel Malod-Dognin  
📧 noel.malod@mbzuai.ac.ae

## Overview

L-GRAAL (Lagrangian GRAphlet-based network Aligner) is a global network alignment tool that aligns biological networks by combining:

- **Lagrangian relaxation**: An efficient optimization solver
- **Graphlet-based scoring**: Statistics of small induced subgraphs (graphlets) to capture network topology

## Resources

- **[Supplementary Material](http://www0.cs.ucl.ac.uk/staff/natasa/L-GRAAL/L-GRAAL_supplement.pdf)** (PDF)
- **[Predicted Interactions: Yeast-Human](http://www0.cs.ucl.ac.uk/staff/natasa/L-GRAAL/Predicted_interactions.xls)** (XLS)
- **[PPI Dataset](http://www0.cs.ucl.ac.uk/staff/natasa/L-GRAAL/PPI_Dataset.7z)** - Networks, graphlet degree signatures, and sequences

*Note: If download links don't work when clicked, copy and paste the URLs directly into your browser's address bar.*

## Requirements

To align two PPI networks with L-GRAAL, you need:

1. Two network files in LEDA format ([format description](link))
2. Two graphlet degree signature files (`.ndump2` files produced by the provided `ncount4` software)
3. Sequence alignment scores file (1-evalues, -log(evalues), or bitscores) between proteins

## Installation

```bash
git clone https://github.com/przulj-lab/L-GRAAL.git
cd L-GRAAL
```

## Usage

### Basic Command

```bash
./L-GRAAL -Q RNorvegicus.gw -T SPombe.gw -q RNorvegicus.ndump2 -t SPombe.ndump2 -B blast_evalues.txt -o my_output
```

### Parameters

- `-Q` : Query network file (LEDA format)
- `-T` : Target network file (LEDA format)
- `-q` : Query network graphlet degree signatures (.ndump2)
- `-t` : Target network graphlet degree signatures (.ndump2)
- `-B` : BLAST sequence alignment scores file
- `-o` : Output alignment file

### Full Parameter List

For complete list of parameters:
```bash
./L-GRAAL.exe -h
```

## Example

Aligning *Rattus norvegicus* and *Schizosaccharomyces pombe* networks:

```bash
./L-GRAAL -Q RNorvegicus.gw \
          -T SPombe.gw \
          -q RNorvegicus.ndump2 \
          -t SPombe.ndump2 \
          -B blast_evalues.txt \
          -o RNorvegicus_SPombe_alignment
```

## Input File Formats

### LEDA Format
Network files must be in LEDA graph format. See [format description](link) for details.

### Graphlet Degree Signatures
Generate `.ndump2` files using the provided `ncount4` software included in this package.

### Sequence Scores
BLAST alignment scores between proteins, formatted as:
- 1-evalues, or
- -log(evalues), or
- bitscores

## Other Network Alignment Algorithms

- **[HubAlign](https://home.ttic.edu/~hashemifar/#softwares)**
- **[Spinal](https://code.google.com/archive/p/spinal/)**
- **[Piswap](https://cb.csail.mit.edu//piswap/webserver/)**
- **[Ghost](https://www.cs.cmu.edu/~ckingsf/software/ghost/)**
- **[MI-GRAAL](https://www.ncbi.nlm.nih.gov/pubmed/23047559)**
- **[IsoRank](https://cb.csail.mit.edu//mna/)**

## Citation

If you use this code or data in your research, please cite:

```
Noël Malod-Dognin, Nataša Pržulj,
L-GRAAL: Lagrangian graphlet-based network aligner,
Bioinformatics, Volume 31, Issue 13, July 2015, Pages 2182–2189,
https://doi.org/10.1093/bioinformatics/btv130
```

## Contact

For questions or issues, please contact Dr. Noel Malod-Dognin at noel.malod@mbzuai.ac.ae
