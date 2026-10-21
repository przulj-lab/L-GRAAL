<div align="center">

<img src="images/header02.jpg" width="100%">

# Aligning Biological Networks with L-GRAAL (Lagrangian GRAphlet-based Network Aligner)

**Noël Malod-Dognin and Nataša Pržulj**

Corresponding author: Dr. N. Malod-Dognin, noel.malod@mbzuai.ac.ae

<img src="images/net_align.jpg" width="450">

</div>

L-GRAAL is a global network alignment tool that combines an efficient solver based on Lagrangian relaxation with a scoring function based on the statistics of small induced subgraphs called graphlets.

## Downloads

- [L-GRAAL for Linux x64](https://github.com/przulj-lab/L-GRAAL/releases/download/v1.0/L-GRAAL-Software-package.7z)
- [Supplementary material (PDF)](https://github.com/przulj-lab/L-GRAAL/releases/download/v1.0/L-GRAAL_supplement.pdf)
- [Predicted interactions between yeast and human (XLS)](https://github.com/przulj-lab/L-GRAAL/releases/download/v1.0/Predicted_interactions.xls)
- [PPI dataset](https://github.com/przulj-lab/L-GRAAL/releases/download/v1.0/PPI_Dataset.7z): networks, graphlet degree signatures, and sequences

## How to run L-GRAAL

To align two PPI networks, you need 5 input files:
- the two network files, in LEDA format (`.gw`, see [format description](https://web.archive.org/web/http://www.algorithmic-solutions.info/leda_guide/graphs/leda_native_graph_fileformat.html))
- two files with the graphlet degree signatures of the networks' nodes (the `.ndump2` files produced by the provided `ncount4` software)
- a file with the sequence alignment scores (1 − e-values, −log(e-values), or bitscores) between the proteins of the two networks

Example, aligning *R. norvegicus* and *S. pombe*:
```bash
./L-GRAAL -Q RNorvegicus.gw -T SPombe.gw -q RNorvegicus.ndump2 -t SPombe.ndump2 -B blast_evalues.txt -o my_output
```

Run `./L-GRAAL.exe -h` for the full list of parameters.

## Other network alignment algorithms

- [HubAlign](https://home.ttic.edu/~hashemifar/#softwares)
- [Spinal](https://code.google.com/archive/p/spinal/)
- [Magna](https://academicweb.nd.edu/~cone/MAGNA++/?utm_campaign=redirect&utm_medium=web&utm_source=www3.nd.edu)
- [Piswap](https://cb.csail.mit.edu/cb/piswap/webserver/)
- [NetAl](http://bioinf.modares.ac.ir/software/netal/)
- [Ghost](https://www.cs.cmu.edu/~ckingsf/software/ghost/)
- [Natalie](https://www.mi.fu-berlin.de/w/LiSA/Natalie)
- [MI-GRAAL](https://github.com/przulj-lab/MI-GRAAL)
- [IsoRank](https://cb.csail.mit.edu/cb/mna/)

## Citation

N. Malod-Dognin and N. Pržulj. L-GRAAL: Lagrangian graphlet-based network aligner. *Bioinformatics* 31(13), 2182–2189 (2015). https://doi.org/10.1093/bioinformatics/btv130
